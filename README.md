# TryToUseTableview
//
//  ViewController.swift
//  TryToUseTableview
//
//  Created by Jep Xia on 16/6/6.
//  Copyright © 2016年 Jep Xia. All rights reserved.
//

import UIKit

class ViewController: UIViewController, UITableViewDelegate, UITableViewDataSource {

    @IBOutlet
    var tableView: UITableView?
    var items: [String] = ["China", "USA", "Russia"]
    
    override func viewDidLoad()
    {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
        self.tableView!.registerClass(UITableViewCell.self, forCellReuseIdentifier: "cell")
    }
    
    override func didReceiveMemoryWarning()
    {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }
    
    func tableView(tableView: UITableView, numberOfRowsInSection section: Int) -> Int
    {
        return self.items.count;
    }
    
    func tableView(tableView: UITableView, cellForRowAtIndexPath indexPath: NSIndexPath) -> UITableViewCell
    {
        let cell:UITableViewCell = self.tableView!.dequeueReusableCellWithIdentifier("cell")! as UITableViewCell
        
        cell.textLabel!.text = self.items[indexPath.row]
        
        return cell

    }
}
