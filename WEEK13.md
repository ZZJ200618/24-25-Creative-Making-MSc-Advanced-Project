# Week 13 — Unity Prototype Development
Objective: Implement the first three gameplay scenes and complete the Minimum Viable Narrative Prototype (MVP).

---

## 1.Visual Direction Update — Collage + Mime-style Monochrome
<img width="1920" alt="1" src="https://git.arts.ac.uk/user-attachments/assets/28bd7631-f3a6-4ffe-90c4-930c7ff21bea" />

This week I revised the overall art direction:

New Visual Style:

- Black-and-white collage aesthetic

- Silent-mime theatrical tone

- Cut-out textures + fragmented composition

- High-contrast silhouettes resembling early silent-stage performance

Reasons for the Shift:

Better communicates themes of control, objectification, and fragmented identity，Collage visuals align with the game’s narrative of being “assembled” or “constructed”

Mime-like monochrome removes distractions, focusing attention on gesture + emotion，Stronger alignment with puppet-theatre symbolism and surveillance motifs，This update will influence all future prototype scenes.

Updated Secene:
![19](https://git.arts.ac.uk/user-attachments/assets/4d9ddbce-117c-4030-83b3-4ab14cdf875a)
<img width="1920" alt="20" src="https://git.arts.ac.uk/user-attachments/assets/9a4fc680-0ae3-48bd-b89f-09ef3313e26c" />
<img width="1920" alt="2" src="https://git.arts.ac.uk/user-attachments/assets/faa24b1f-c556-4461-b00a-e671b86c68ca" />
<img width="1920" alt="3" src="https://git.arts.ac.uk/user-attachments/assets/5f36ed0c-eadd-474d-a449-19dd5686cdc9" />
![4](https://git.arts.ac.uk/user-attachments/assets/4a646d25-e74c-4dca-8134-1811355ad082)
<img width="1920" alt="23" src="https://git.arts.ac.uk/user-attachments/assets/4a4cd276-3872-43da-a27a-714088368cfd" />
<img width="1920" alt="24" src="https://git.arts.ac.uk/user-attachments/assets/814fd613-3a2d-4723-b878-89d08aafe0c7" />
<img width="1920" alt="25" src="https://git.arts.ac.uk/user-attachments/assets/8eebfb92-36f0-4bd7-a0ce-6e94cd4faf01" />
<img width="1920" alt="26" src="https://git.arts.ac.uk/user-attachments/assets/a5826d7e-94f4-4ef7-9a8e-b8586fd8c125" />


## 2. Prototype Build — Scenes 1–3

### Scene 1 — Starting Village
- [x] WASD movement + camera follow  
- [x] NPC placeholders + dialogue system  
- [x] Opening narrative triggers (birth, surveillance cues)  
- [x] Village exit + guidance arrow prototype

### Scene 2 — Assigned Mission
- [x] IRWiG / Bechdel-inspired assignment logic  
- [x] “Instrumental role” dialogue framing  
- [x] Forced progression (choices do not alter result)  
- [x] Cutscene placeholder (fade → text → spawn)

![27](https://git.arts.ac.uk/user-attachments/assets/3e27250c-518b-4d75-992b-77d3bd5c523a)

---

## 3. Base Interaction Systems

### TypeWriterEffect
```csharp
using UnityEngine;
using UnityEngine.SceneManagement;
using TMPro;
using System.Collections;

public class DialogManager : MonoBehaviour
{
    [Header("Dialog")]
    public TextMeshProUGUI dialogText;    
    public string[] dialogs;              
    public float typingSpeed = 0.03f;      

    private int currentIndex = 0;         
    private bool isTyping = false;         

    void Start()
    {
        dialogText.text = "";
        StartCoroutine(TypeText(dialogs[currentIndex]));
    }

    void Update()
    {
        if (Input.GetMouseButtonDown(0))
        {
            if (isTyping)
            {
                StopAllCoroutines();
                dialogText.text = dialogs[currentIndex];
                isTyping = false;
            }
            else
            {
                currentIndex++;

                if (currentIndex < dialogs.Length)
                {
                    StartCoroutine(TypeText(dialogs[currentIndex]));
                }
                else
                {
                    LoadNextScene();
                }
            }
        }
    }

    IEnumerator TypeText(string text)
    {
        isTyping = true;
        dialogText.text = "";

        foreach (char c in text)
        {
            dialogText.text += c;
            yield return new WaitForSeconds(typingSpeed);
        }

        isTyping = false;
    }

    void LoadNextScene()
    {
        int nextSceneIndex = SceneManager.GetActiveScene().buildIndex + 1;
        if (nextSceneIndex < SceneManager.sceneCountInBuildSettings)
        {
            SceneManager.LoadScene(nextSceneIndex);
        }
        else
        {
            Debug.LogWarning("noload");
        }
    }
}
```

### Select the button to jump to the next scene
```csharp
using UnityEngine;
using UnityEngine.EventSystems;
using UnityEngine.SceneManagement;

public class EnterNextSceneButton : MonoBehaviour, IPointerEnterHandler, IPointerExitHandler, IPointerClickHandler
{
    [Header("outline")]
    public GameObject borderImage; 

    public void OnPointerEnter(PointerEventData eventData)
    {
        if (borderImage != null)
            borderImage.SetActive(true);
    }

    public void OnPointerExit(PointerEventData eventData)
    {
        if (borderImage != null)
            borderImage.SetActive(false);
    }

    public void OnPointerClick(PointerEventData eventData)
    {
        int currentIndex = SceneManager.GetActiveScene().buildIndex;
        int nextIndex = currentIndex + 1;

        if (nextIndex < SceneManager.sceneCountInBuildSettings)
        {
            SceneManager.LoadScene(nextIndex);
        }
        else
        {
            Debug.LogWarning("noload");
        }
    }
}
```

### Lefttrriger
```csharp
using UnityEngine;
using UnityEngine.SceneManagement;

public class EdgeInteraction : MonoBehaviour
{
    [Header("left")]
    public GameObject dialogPanel;        

    [Header("right")]
    public string nextSceneName;          
    private bool playerInLeftTrigger = false;
    private bool playerInRightTrigger = false;

    private void Start()
    {
        if (dialogPanel != null)
            dialogPanel.SetActive(false); 
    }

    private void Update()
    {
       
        if (playerInLeftTrigger && Input.GetMouseButtonDown(0))
        {
            if (dialogPanel != null && dialogPanel.activeSelf)
            {
                dialogPanel.SetActive(false);
            }
        }

 
        if (playerInRightTrigger && Input.GetMouseButtonDown(0))
        {
            LoadNextScene();
        }
    }


    private void OnTriggerEnter2D(Collider2D other)
    {
        if (!other.CompareTag("Player")) return;

     
        if (gameObject.CompareTag("LeftTrigger"))
        {
            playerInLeftTrigger = true;
            if (dialogPanel != null)
                dialogPanel.SetActive(true);
        }

        else if (gameObject.CompareTag("RightTrigger"))
        {
            playerInRightTrigger = true;
        }
    }

    private void OnTriggerExit2D(Collider2D other)
    {
        if (!other.CompareTag("Player")) return;

        if (gameObject.CompareTag("LeftTrigger"))
        {
            playerInLeftTrigger = false;
            if (dialogPanel != null)
                dialogPanel.SetActive(false);
        }
        else if (gameObject.CompareTag("RightTrigger"))
        {
            playerInRightTrigger = false;
        }
    }

  
    void LoadNextScene()
    {
        if (!string.IsNullOrEmpty(nextSceneName))
        {
            SceneManager.LoadScene(nextSceneName);
        }
        else
        {
            int nextIndex = SceneManager.GetActiveScene().buildIndex + 1;
            if (nextIndex < SceneManager.sceneCountInBuildSettings)
            {
                SceneManager.LoadScene(nextIndex);
            }
            else
            {
                Debug.LogWarning("no load");
            }
        }
    }
}
```

### Righttrrigger
```csharp
using UnityEngine;
using UnityEngine.SceneManagement;

public class RightTriggerSimple : MonoBehaviour
{
    [Header("next")]
    public string nextSceneName;

    private bool triggered = false; 

    private void OnTriggerEnter2D(Collider2D other)
    {
        if (triggered) return; 

        if (other.CompareTag("Player"))
        {
            triggered = true;
            Debug.Log(" Playerintoright");
            LoadNextScene();
        }
    }

    void LoadNextScene()
    {
        if (!string.IsNullOrEmpty(nextSceneName))
        {
            SceneManager.LoadScene(nextSceneName);
        }
        else
        {
            int nextIndex = SceneManager.GetActiveScene().buildIndex + 1;
            if (nextIndex < SceneManager.sceneCountInBuildSettings)
                SceneManager.LoadScene(nextIndex);
            else
                Debug.LogWarning("no load");
        }
    }
}
