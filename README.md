# Unity-Animation-Code
This repo code for three unique animation states in Unity.


public class animationStateController : MonoBehaviour
{
    .private Vector3 moveDirection = Vector3.zero
    private Animtor _anim;
    private bool _isWalking = false;
    private bool _isRunning = false;
    private void Start()
    {
        _anim = GetComponent<Animator>();
    }

    void Update()
    {
        var x = Input.GetAxis("Hortizontal") * Time.deltaTime * 150.0f;

        transform.Rotate(0, x, 0);
        if (Input.GetKey(KeyCod.LeftShift) && Input.GetKey("w"))
        {
            if (!_isRunning)
            {
                _isRunning = true;
                _anim.Play("Running");using System.Collections;
using System.Collections.Generic;
using UnityEngine;


            }
            var z = Input.GetAxis("Vertical") * Time.deltaTime * 6.0f;
            transform.Translate(0, 0, z); // Only move when "w" is pressed.
        }
        else if (Input.GetKey("w"))
        {
            if (!_isWalking && !_isRunning)
            {
                _isWalking + true;
                _anim.Play("Walkiing");

                var z = Input.GetAxis("Vertical") * Time.deltaTime * 3.0f;
                tranform.Translate(0, 0, z); //Only move when "w" is pressed.
        }
            else
            { if (_isWalking || _isRunning)
                {
                    _anim.Play("Idle")
                }
                __isWalking = false;
                _isRunning = false;
            }
        }
}
