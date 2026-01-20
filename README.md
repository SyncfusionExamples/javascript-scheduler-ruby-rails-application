<!--
  howto.md
  A step-by-step guide to integrate Ruby on Rails with Syncfusion TS Scheduler
-->
## How to Integrate Ruby on Rails with Syncfusion Scheduler
This repository contains a sample full-stack application demonstrating how to display events in syncfuison Scheduler component using Ruby on Rails.

## Prerequisites
- Ruby - (3.2.2)
- Node JS - (>=18.13.0)
- Yarn - (>=1.22.19)

## Project Structure
```
├── README.md                  # This guide
├── postcss.config.js
├── package.json                  
├── test       #Testing the functionality      
│   ├── events_controller_test.rb  
│   ├── schedule_controller_test.rb
├── app 
│    ├── javascript   #Main JavaScript entry point that initializes frontend behavior
│    │   ├── application.js
│    │   ├── controllers
│    │   │   ├── index.js
     └── views
         ├── layouts
         │   ├── application.html.erb  #Base HTML layout wrapping all views
         └── welcome
             └── index.html.erb  # View template for the welcome page
```

## Project Setup
### Installation
1. #### Clone the project
    Clone the project from the repository by creating a fork and branch.
2. #### Ruby setup
    You can install the Ruby from the following link.
    [`https://www.ruby-lang.org/en/downloads/`](https://www.ruby-lang.org/en/downloads/) 
    Then Install gem using below commands
    ```
    gem install rails
    ```
3. #### Install dependencies:
   	```bash
    npm install
        or
    yarn install
    ```
### Running the Application
1. Navigate to javascript-scheduler-ruby-rails-application folder.
    ```bash
    cd javascript-scheduler-ruby-rails-application
    ```
2. Start the Scheduler Frontend
    ```bash
    rails server
    ```
3. Navigate to `http://localhost:3000` in your browser. (or) Ctrl + click the link in your terminal


## Output
![Frontend Preview](./SampleOutput.png)

## Troubleshooting
- **Version error**: Check and install the current version as by prerequistes.
- **Port already in use**: Clear all the previous running applications in both browser and command prompt.

## Creating Ruby on Rails Project With Syncfusion Scheduler

### 1. Create your folder-directory.
Create a folder with your own application name.

Run the below command in your project terminal to create a directory.
```bash    
    mkdir rails-ts-scheduler
```

### 2. Navigate to your folder.
```bash
    cd rails-ts-scheduler
```

### 3. Creation of rails Project
Create a new rails project in your folder using the below command.
```bash
    rails new . --webpack --database=sqlite3
```

### 4. Create package.json file 
To create package.json file use the following command.
```bash
    bundle add jsbundling-rails
```

### 5. Add Scripts
To add esbuild scripts, app/javascript/application.js use the following command
```bash
    rails javascript:install:esbuild
```

### 6. Installation of syncfusion dependencies
Install the syncfusion dependencies by the following commands.
```bash
    yarn add @syncfusion/ej2-schedule
                or
    npm add @syncfusion/ej2-schedule
```
### 7. Add CSS styles
Add the Styles in app/javascript/application.js

Import the necessary css styles from syncfusion documentatoion from the below link
```bash
    https://ej2.syncfusion.com/documentation/schedule/getting-started

```

### 8. Creation of event models
Create a event folder to save the events in the database.
```bash 
    rails generate model Event title:string start:datetime end:datetime description:text
```
To create a table in the database
```bash 
rails db:migrate
```

### 9. Create controller and Routes
To Create the EventsController, which handles event-related routes and API actions used by the Syncfusion Scheduler.
```bash   
    rails generate controller Events
```

### 10. Creation of Home folder
Create the folder Home and index.html
```bash  
    rails generate controller Home index
```

## 12. Update the code in index.html
Update the file app/views/Home/index.html or refer syncfusion documentation for different scheduler
     https://ej2.syncfusion.com/documentation/schedule/getting-started
```bash   
    <section>
    <script src="https://cdn.syncfusion.com/ej2/32.1.24/dist/ej2.min.js" type="text/javascript"></script>
    <link href="https://cdn.syncfusion.com/ej2/32.1.24/material.css" rel="stylesheet">
    </section>
    <section>
    <div id="Schedule"></div>
    <script>
        var scheduleObj = new ej.schedule.Schedule({
            height: '550px',
            width: '100%',
            selectedDate: new Date(2023, 6, 13),
            eventSettings: {
                dataSource: [{
                    Id: 1,
                    Subject: 'Meeting',
                    StartTime: new Date(2023, 6, 13, 10, 0),
                    EndTime: new Date(2023, 6, 13, 12, 30)
                }]
            }       
        });
        scheduleObj.appendTo('#Schedule');
    </script>
    </section>
```

### 13.Run the application
Run the application using the following command.
```bash 
    rails server
```
    
    

