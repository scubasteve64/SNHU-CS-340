# SNHU-CS-340

CS 340 README


About the Project/Project Title
Hello! This Project is for my work done for Grazioso Salvare. I represent a Software Engineer for Global Rain. This project was to create a software application that can identify and categorize available Dogs for multiple uses as well as visual data represented by charts and maps using CRUD methodology.

Motivation
This project was a job meant to satisfy a client. The organization I work for creates custom Software applications and development processes.

Getting Started
To get started, you’ll want to make sure your Mongo DB and Python are linked together, using the “pip install pymongo”

Installation
Tools you will need for this project is Bash CLI, Jupyter Notebook, and the ability to create a .PY file.

Usage

Code Example
  "from aac_crud import AnimalShelter\n",
,

  "username = 'aacuser'\n",
  "password = 'SNHU1234'\n",
  "host = 'nv-desktop-services.apporto.com'\n",
  "port = 31240\n",
  "database = 'AAC'\n",
  "collection = 'animals'\n",
  "\n",
  "# Instantiate CRUD Class\n",
  "crud = AnimalShelter(username, password, host, port, database, collection)\n",

def update_dashboard(filter_type):
    if filter_type is None:
        return
    df = None
    
    if filter_type == 'Water':
        df = pd.DataFrame.from_records(db.read(
                    { "$and": [
                        {"$or": [
                            {'breed' : {"$regex": 'Labrador Retriever Mix'}},
                            {'breed' : {"$regex": 'Chesapeake'}},
                            {'breed' : {"$regex" : 'Newfoundland'}}]},
                        {'sex_upon_outcome':'Intact Female'},
                        { "$and": [
                            {'age_upon_outcome_in_weeks': {"$gt": 26}},
                            {'age_upon_outcome_in_weeks': {"$gt": 156}}
                    ]}
                    ]}))
    elif filter_type == 'Mountain':
        df = pd.DataFrame.from_records(db.read(
                    { "$and": [
                        {"$or": [
                            {'breed': {"$regex":'German Shepherd'}},
                            {'breed': {"$regex":'Alaskan Malamute'}},
                            {'breed': {"$regex":'Old English Sheepdog'}},
                            {'breed': {"$regex":'Siberian Husky'}},
                            {'breed': {"$regex":'Rottweiler'}}]},
                        {'sex_upon_outcome': 'Intact Male'},
                        { "$and": [
                            {'age_upon_outcome_in_weeks':{"$gt": 26}},
                            {'age_upon_outcome_in_weeks':{"$gt": 156}},
                        ]}
                ]}))
    elif filter_type == 'Disaster':
            df = pd.DataFrame.from_records(db.read(
                { "$and": [
                        {"$or": [
                            {'breed': {"$regex":'Doberman Pinscher'}},
                            {'breed': {"$regex":'German Shepherd'}},
                            {'breed': {"$regex":'Golden Retriever'}},
                            {'breed': {"$regex":'Bloodhound'}},
                            {'breed': {"$regex":'Rottweiler'}}]},
                        {'sex_upon_outcome': 'Intact Male'},
                        { "$and": [
                            {'age_upon_outcome_in_weeks':{"$gt": 20}},
                            {'age_upon_outcome_in_weeks':{"$gt": 300}},
                        ]}
                ]}))
    else:
        df = pd.DataFrame.from_records(db.read({'animal_type':'Dog'}))

    df.drop(columns=['_id'],inplace=True)
    return df.to_dict('records')

Tests
You can test the CRUD objective using Jupyter and Python. Doing this can show possible outcomes and errors if there are any. I went through multiple steps trying to make sure every syntax was in place properly and that there were no errors. The nice part about Jupyter notebook is that it will inform me where an issue may lie, and allows me to correct it so that the final function will work.


Screenshots
 
 
  
 
 
.

Contact
Your name: Stephan Hill
![image](https://github.com/user-attachments/assets/6e9fea65-cb81-4a11-872f-3a252d4f475f)
