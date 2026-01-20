<!--
  howto.md
  A step-by-step guide to integrate Ruby on Rails with Syncfusion TS Scheduler
-->
# How to Integrate Ruby on Rails with Syncfusion TS Scheduler
This repository contains a sample full-stack application demonstrating how to display events in syncfuison TS Scheduler component using Ruby on Rails. The TS frontend provides a responsive UI for viewing and managing calendar events.

## Prerequisites
-Ruby - (3.2.2)
-Node JS - (>=18.13.0)
-Yarn - (>=1.22.19)

## Project Structure
```
├── README.md                  # This guide
├── postcss.config.js
├── package.json                  
├── package-lock.json
├── test             
│   ├── events_controller_test.rb
│   ├── schedule_controller_test.rb
├── app
│    ├── javascript   
│    │   ├── application.js
│    │   ├── controllers
│    │   │   ├── index.js
     └── views
         ├── layouts
         │   ├── application.html.erb
         └── welcome
             └── index.html.erb
```

## Ruby setup
### Installation
1. ## Ruby setup
    You can install the Ruby from the following link.
    [`https://www.ruby-lang.org/en/downloads/`](https://www.ruby-lang.org/en/downloads/) 
2. ## Install Rails
    ```
    gem install rails
    ```
3. ## Install dependencies:
   	```bash
    npm install
    ```
4. ## Install dependencies:
   	```bash
    yarn install
    ```
## Running the Application
1. Navigate to javascript-scheduler-ruby-rails-application folder
    ```bash
    cd javascript-scheduler-ruby-rails-application
    ```
2. Start the Scheduler FrontEnd
    ```bash
    rails server
    ```
3. Navigate to `http://localhost:3000` in your browser. (or) Ctrl + click the link in your terminal


## OutputPreview
![Frontend Preview](./SampleOutput.png)

## Troubleshooting
- **Version error**: Check and install the current version as by prerequistes.
- **Port already in use**: Clear all the previous running applications in both browser and command prompt.

## Rails project creation Setup from the Scratch

## 1. Create your folder.
Create a folder with your own application name.


## 2. Create a Directory
Run the below command in your project terminal to create a directory.
```bash    
    mkdir rails-ts-scheduler
```

## 3. Navigate to your folder.
```bash
    cd rails-ts-scheduler
```

## 4. Creation of rails Project
Create a new rails project in your folder using the below command.
```bash
    rails new . --webpack --database=sqlite3
```

## 5. Create package.json file 
To create package.json file use the following command.
```bash
    bundle add jsbundling-rails
```

## 6. Add Scripts
To add esbuild scripts, app/javascript/application.js use the following command
```bash
    rails javascript:install:esbuild
```

## 7. Installation of syncfusion dependencies
Install the syncfusion dependencies by the following commands.
```bash
    
    yarn add @syncfusion/ej2-base
    yarn add @syncfusion/ej2-schedule
    yarn add @syncfusion/ej2-buttons @syncfusion/ej2-calendars

```

## 8. Add CSS styles
Add the Styles in app/javascript/application.js.

import the necessary css styles from syncfusion documentatoion from the below link
```bash
    https://ej2.syncfusion.com/documentation/schedule/getting-started

```

## 9. Creation of event models
To Create the event model in your application use the below commands.
```bash 
    rails generate model Event title:string start:datetime end:datetime description:text
    rails db:migrate

```

## 10. Create controller and Routes
To Create Events Controller + Routes use following commands.
```bash   
    rails generate controller Events
```

## 11. Creation of Home folder
Create the folder Home and index.html
```bash  
    rails generate controller Home index
```

## 12. Update the code in index.html
Update the file app/views/Home/index.html or refer syncfusion documentation for different scheduler
     https://ej2.syncfusion.com/documentation/schedule/getting-started
```bash
    
    <section>
    <script src="https://cdn.syncfusion.com/ej2/22.1.38/dist/ej2.min.js" type="text/javascript"></script>
    <link href="https://cdn.syncfusion.com/ej2/22.1.38/material.css" rel="stylesheet">
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

## 13.Run the application
Run the application using the following command.
```bash 
    rails server
```
    
    

