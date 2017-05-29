# Plugin MyTrooperS
This plugin requires jQuery 2.2.4 or higher.

## Authentification
        mts.auth.init(client_id: String, client_secret: String, login: String, password: String, dev_mode: Bool)
**Required** - *Init the connexion to MTS API and allows you to call routes*

## Get Owner
        mts.user.get(email: String, callback: Function(response));
**Required** - *Get the User entity from our DataBase to set him as the run's owner* - callback response = {id: Int, email: String}

## Set Customer
		mts.run.setCustomer(firstname: String, lastname: String, phone: String, mail: String)
*Set the customer Entity*

## Set Date
		mts.run.setDate(date: String)
*Set the run date*  
date: "yyyy-MM-ddThh:mm"

## Add Step
		mts.run.addStep(address: String, floors: Int, elevator: Int, contactName: String, contactPhone: String)
*Add a step to the run*
floors: from -1 to 10 (-1 is the pavement)

## Add Stuff
		mts.run.addStuff(name: String, step: Int, depositStep: Int, volume: Float, type: String, nb: Int)
*Add a stuff to the run*  
volume: m^3  
type: "cardboard", "normal", "heavy", "super_heavy"

## Price
		mts.run.price(callback: Function(response))
*Get the price of the run if all steps and stuffs are set* - callback response = {tt: Float, pp1: Float, pp2: Float}

## Create run
		mts.run.create(callback: Function(response))
*Create run in database* - callback response = {id: Int, createdAt: Date, date: Date, carTypeRequest: String, flag: {id: Int, name: String}, origin: String}

## Create Form
		mts.form.generate(id: String, callback: Function(response))
*Generate a HTML form with all the infos already set* - callback response = {id: Int, createdAt: Date, date: Date, carTypeRequest: String, flag: {id: Int, name: String}, origin: String}  
The callback method will be executed when the run will be created after clicking on the "Create Run" button.