# error

	var currentCriteria:CriteriaType!
	var data:[CriteriaType:Int] = [
		.Province: -1,
		.District: -1,
		.Dealer: 0
		]
	
    override func viewDidLoad() {
        super.viewDidLoad()

        // Do any additional setup after loading the view.
    }
    
    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }
	
	@IBAction func onDismiss(sender: AnyObject) {
		self.dismissViewControllerAnimated(true, completion: nil)
	}
	
	func setData(dataId:Int, dataLabel:String) {
		//
		print("Set: \(dataId) = \(dataLabel)")
		data[currentCriteria] = dataId
        if currentCriteria == .Province { // This is Line error : Type of expression is ambiguous without more context
			provinceSelectedLabel.text = dataLabel
			districtSelectedLabel.text = "โปรดเลือก"
			data[.District] = -1;
			//if let d = data[.District] {
		}
		if currentCriteria == .District { // This is Line error : Type of expression is ambiguous without more context
			districtSelectedLabel.text = dataLabel
		}
		if currentCriteria == .Dealer { // This is Line error : Type of expression is ambiguous without more context
			dealerSelectedLabel.text = dataLabel
		}
	}
