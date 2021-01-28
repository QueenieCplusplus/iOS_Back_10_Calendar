# iOS_Back_10_Calendar
to popover a calendar in full screen on iPhone or as a small box in Plus or iPad


![](https://raw.githubusercontent.com/QueenieCplusplus/iOS_Back_10_Calendar/main/output%201.png)

![](https://github.com/QueenieCplusplus/iOS_Back_10_Calendar/raw/main/output%202.png)



code:


      //
      //  ViewController.swift
      //  KatesPopoverCalendarApp
      //
      //  Created by KatesAndroid on 2021/1/28 PM 2: 40 ~ 3: 20
      //
      import UIKit

      class ViewController: UIViewController, UIPopoverControllerDelegate, UIPopoverPresentationControllerDelegate {

          override func viewDidLoad() {
              super.viewDidLoad()

          }

          override func prepare(for segue: UIStoryboardSegue, sender: Any?) {

              let pop = segue.destination.popoverPresentationController

              // maybe is the UIButtonItem
              if sender is UIButton {
                  pop?.sourceRect = (sender as! UIButton).bounds
              }

              pop?.delegate = self
          }

          // turn off the mobile-screen-size detection
          // then popOver display replaces the full screen in small-screen-size target
          func adaptivePresentationStyle(for controller: UIPresentationController) -> UIModalPresentationStyle {
              return .none
          }

      }
