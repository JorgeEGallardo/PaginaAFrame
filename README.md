using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class SCR : MonoBehaviour
{
    public TextMesh xd;
    double cooldownCounter = 0;
    bool coolingdown = false;
    bool open=false;
    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame
    void OnTriggerStay()
    {
        if (!open)
        {
            if (!coolingdown)
            {
                if (Input.GetKey(KeyCode.Alpha0) || Input.GetKey(KeyCode.Keypad0))
                    xd.text = xd.text + 0;
                if (Input.GetKey(KeyCode.Alpha1) || Input.GetKey(KeyCode.Keypad1))
                    xd.text = xd.text + 1;
                if (Input.GetKey(KeyCode.Alpha2) || Input.GetKey(KeyCode.Keypad2))
                    xd.text = xd.text + 2;
                if (Input.GetKey(KeyCode.Alpha3) || Input.GetKey(KeyCode.Keypad3))
                    xd.text = xd.text + 3;
                if (Input.GetKey(KeyCode.Alpha4) || Input.GetKey(KeyCode.Keypad4))
                    xd.text = xd.text + 4;
                if (Input.GetKey(KeyCode.Alpha5) || Input.GetKey(KeyCode.Keypad5))
                    xd.text = xd.text + 5;
                if (Input.GetKey(KeyCode.Alpha6) || Input.GetKey(KeyCode.Keypad6))
                    xd.text = xd.text + 6;
                if (Input.GetKey(KeyCode.Alpha7) || Input.GetKey(KeyCode.Keypad7))
                    xd.text = xd.text + 7;
                if (Input.GetKey(KeyCode.Alpha8) || Input.GetKey(KeyCode.Keypad8))
                    xd.text = xd.text + 8;
                if (Input.GetKey(KeyCode.Alpha9) || Input.GetKey(KeyCode.Keypad9))
                    xd.text = xd.text + 9;



                coolingdown = true;
                cooldownCounter = 0.2;
            }

            else
            {
                cooldownCounter -= Time.deltaTime;
                if (cooldownCounter <= 0)
                {
                    coolingdown = false;
                }
            }

            if (xd.text.Length > 3)
                xd.text = "";

            if (xd.text == "371")
            {
                xd.text = "oh si";
                open = true;
            }

        }
    }
}
