# leaddesk 

A demo module created by Neil Yashinsky to highlight the value of the Objects and its connected capabilities provide.


## Demonstration of Liferay Objects
### Link to Something else maybe

As background, this Company is rolling out a new product.  To drive the sales process for a new product they want a means to generate, track, manage and convert leads to orders. In this example, those leads can get created externally or internally to Liferay or both.  The leads will be distributed across 3 teams: inside sales team, mid-market, and the enterprise team.

To handle the distribution of the leads, a "lead desk" is created where the leads come in in this example let's say from a website, trade show kiosk or promotional giveaway, smart speaker type device where you can request a quote.  Based on the volume of orders, and geographical distribution (represented by timezones), we will dristrbute the leads to the appropriate sales team.  The sales team includes:

Inside Sales team:
Multi-rep view where any rep can work any deal

Mid-market:
Regional distribution drives who gets what leads

Enterprise:
Assigned accounts.

The leads are tracked across the purchase lifecycle: new, quoted, created, paid, shipped.  Once an order has been shipped it doesn't need to be tracked.  



# 7.4 Setup

## Liferay Object

First add the picklists, then the objects.  

1. Create a Picklist called "LeadStanding" 

| Field       | Key         |
| :---        | :---        |
| new         | new         |
| quoted      | quoted      |
| created     | created     |
| paid        | paid        |
| shipped     | shipped     |

2. Create a picklist called Units
| Field       | Key         |
| :---        | :---        |
| 1 - 100     | 1       	|
| 101 - 1000  | 100		    |
| 1000+		  | 1000	    |


3. Create a picklist called Timezone
| Field       | Key         |
| :---        | :---        |
| Eastern     | Eastern    	|
| Central	  | Central	    |
| Mountain	  | Mountain    |
| Pacific	  | Pacific  	|


4. Create Lead Object.  Set the label as Lead, and the plural label as Leads.  Set the Title  Field as Project Name.  Set the Scope to Company.  Set the Panel Category Key to Commerece>Order Management

5. Object Needs the Fields

| Field     	        | Type            | Required  |
| :---		            |      :----:     |  :----:   |
| Project Name      	| String          | Yes       |
| Product Name      	| String          | No        | this might be deleted TBD
| Project Description	| String          | No        |
| Phone Number			| String          | No        |
| Email					| String          | Yes       |
| Company Name			| String          | No        | this likely should be account when possible
| Estimated Units		| String          | No        |
| Timezone 				| String          | No        |
| Follow Up Date		| String          | No        |
| Status				| String          | Yes       |


6. Build a layout called New Lead.  Name the Layout's basic Info, "New Lead"  Add all the fields using 3 column layout with the following fields:

Row 1: Project Name, Product Name, Company Name
Row 2: Project Description, Phone Number, Email
Row 1: Estimated Units, Timezone, Follow up date
Row 4: Status


# Display Method Options

So many ways to use Remote Apps!! *Yey!*

## Display Method A - Use as separate React App
  
1. Using 'yarn start' start the server. It should hit Liferay's headless API using Basic Authentication (test@liferay.com:test over port 8080)
 
2. Once the server is running, you should be able to see the application running on it's own server at http://localhost:3000/ or similar. 
 
## Display Method B - Remote App's iFrame 
  
1. Once the server is running (se previous step), you should be able to see the application running on it's own server at http://localhost:3000/ or similar. 
    
2. Then, navigate to Remote Apps within Liferay's control panel.
    
3. Create a new Remote App with the following field details:

| Field    | Value                   |
| :---     | :---                    |
| Name     | React Bar Chart         |
| Type     | iFrame                  |
| URL      | http://localhost:3000/  |
    
Save, then this application will be available in your widgets list.

## Display Method C - Remote App's Custom Element
### [Option 1] Javascript Resources Hosted on Remote Server
  
   *NOTE: These JS files are currently being hosted by the React dev server. This is great to point to these files for development because any changes you make to your code will show as soon as you refresh your page in Liferay. When not developing it will be better to run yarn run build and update the URL's with the JS files in your build directory (Options 2 & 3).*  
  




## jQuery Configuration

*Note: Current version required jquery for event handling, dom traversal, and dropdown behavior.*

Enable jQuery in "System Settings" > "Third Party" > "jQuery"


Notes:

We are assuming the following: 

The product in question is generally associated with a project.













