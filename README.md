# Tip Calculator

# Pre-work - Easy Bill

Easy Bill is a tip calculator application for iOS.

Submitted by: Richard Soksann Edwards

Time spent: 2 hours spent in total

## User Stories

The following **required** functionality is complete:

* [ ] User can enter a bill amount, choose a tip percentage, and see the tip and total values.
* [ ] User can select between tip percentages by tapping different values on the segmented control and the tip value is updated accordingly


## Video Walkthrough

Here's a walkthrough of implemented user stories:

https://recordit.co/KeUaAeXJjf

GIF created with Recordit

## Notes

I'd say the hardest thing to do with this pre-work project is deifnitely tyring to keep the objects/actions organized within the code!

## License

    Copyright [2021] [Richard Soksann Edwards]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.


//  ViewController.swift
//  Prework
//
//  Created by Richard Soksann Edwards on 12/25/21.
//

import UIKit

class ViewController: UIViewController {

    @IBOutlet weak var billAmountTextField: UITextField!
    @IBOutlet weak var tipAmountLabel: UILabel!
    @IBOutlet weak var tipControl: UISegmentedControl!
    @IBOutlet weak var totalLabel: UILabel!
    

    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
    }

    @IBAction func calculateTip(_ sender: Any) {
        //The Bill Amount is given through the textfield
        let bill = Double(billAmountTextField.text!) ?? 0
        //Get total tip by multiplying tip * tip percentage
        let tipPercentages = [0.15, 0.18, 0.2]
        let tip = bill * tipPercentages[tipControl.selectedSegmentIndex]
        let total = tip + bill
     
        //Update Tip Amount Label
        tipAmountLabel.text = String(format: "$%.2f", tip)
        //Update Total Amount
        totalLabel.text = String(format: "$%.2f", total)
        
    }
    
}

