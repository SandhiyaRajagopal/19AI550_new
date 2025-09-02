# Ex.No: 6  Implementation of Jumping  behaviour- Unity
### DATE: 02/09/25                                                                            
### REGISTER NUMBER : 212223240146
### AIM: 
To write a program to simulate the process of jumping in Unity.
### Algorithm:
```
1. Create a new 3D Unity project
2. Add a Plane
3. Right-click Hierarchy → 3D Object → Plane → Rename to Ground
4. Add a Cube (Player)
5. Right-click Hierarchy → 3D Object → Cube → Rename to Player
6. Set Position: (0, 0.5, 0)
7. Add a Rigidbody to the Player
8. With the Player selected: Inspector → Add Component → Rigidbody
9. Set Constraints > Freeze Rotation X, Z (optional for stability)
10.Create the Jump Script and Apply the Script Player
11.Run the game
Press Play
Press Spacebar to jump
Your cube should only jump when touching the ground
```
###
**Program **
```
using UnityEngine;

public class PlayerJump : MonoBehaviour
{
    private Rigidbody rb;
    public float jumpForce = 5f;
    private bool isGrounded;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.Space) && isGrounded)
        {
            rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);
            isGrounded = false;
        }
    }

    private void OnCollisionEnter(Collision collision)
    {
        if (collision.gameObject.CompareTag("Ground"))
        {
            isGrounded = true;
        }
    }
}
```
### Output:



![WhatsApp Image 2025-09-02 at 14 52 02_f2ca83e9](https://github.com/user-attachments/assets/67deb44c-8447-408f-a09b-d4c222a1d75a)


![WhatsApp Image 2025-09-02 at 14 51 59_9e66219e](https://github.com/user-attachments/assets/00deb99d-8051-4072-9ea6-fe3963e6bf85)




### Result:
Thus the simple jumping behavior was implemented successfully.
