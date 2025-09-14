# AirBnB Clone - The Console

## Description
This project is a command-line interface (CLI) for managing AirBnB-like objects. It provides functionality to create, read, update, and delete various types of objects including users, states, cities, amenities, places, and reviews.

## Command Interpreter

### How to Start
```bash
./console.py
```

### How to Use
The console provides an interactive command-line interface with the following commands:

- `create <class_name>` - Creates a new instance of the specified class
- `show <class_name> <id>` - Displays the string representation of an instance
- `destroy <class_name> <id>` - Deletes an instance
- `all [class_name]` - Lists all instances (optionally filtered by class)
- `update <class_name> <id> <attribute_name> "<attribute_value>"` - Updates an instance attribute
- `quit` or `EOF` - Exits the program
- `help [command]` - Shows help information

### Examples

#### Creating Objects
```bash
(hbnb) create BaseModel
49faff9a-6318-451f-87b6-910505c55907
(hbnb) create User
2dd6ef5c-467c-4f82-9521-a772ea7d84e9
```

#### Showing Objects
```bash
(hbnb) show BaseModel 49faff9a-6318-451f-87b6-910505c55907
[BaseModel] (49faff9a-6318-451f-87b6-910505c55907) {'id': '49faff9a-6318-451f-87b6-910505c55907', 'created_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903293), 'updated_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903300)}
```

#### Listing All Objects
```bash
(hbnb) all BaseModel
["[BaseModel] (49faff9a-6318-451f-87b6-910505c55907) {'created_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903293), 'id': '49faff9a-6318-451f-87b6-910505c55907', 'updated_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903300)}"]
```

#### Updating Objects
```bash
(hbnb) update BaseModel 49faff9a-6318-451f-87b6-910505c55907 first_name "Betty"
(hbnb) show BaseModel 49faff9a-6318-451f-87b6-910505c55907
[BaseModel] (49faff9a-6318-451f-87b6-910505c55907) {'first_name': 'Betty', 'id': '49faff9a-6318-451f-87b6-910505c55907', 'created_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903293), 'updated_at': datetime.datetime(2017, 10, 2, 3, 11, 3, 49401)}
```

#### Destroying Objects
```bash
(hbnb) destroy BaseModel 49faff9a-6318-451f-87b6-910505c55907
(hbnb) show BaseModel 49faff9a-6318-451f-87b6-910505c55907
** no instance found **
```

## Available Classes
- **BaseModel** - Base class for all other models
- **User** - User information (email, password, first_name, last_name)
- **State** - State information (name)
- **City** - City information (state_id, name)
- **Amenity** - Amenity information (name)
- **Place** - Place information (city_id, user_id, name, description, number_rooms, number_bathrooms, max_guest, price_by_night, latitude, longitude, amenity_ids)
- **Review** - Review information (place_id, user_id, text)

## Data Persistence
All objects are automatically saved to a JSON file (`file.json`) when created, updated, or destroyed. Objects are automatically loaded when the console starts.

## Testing
Run the test suite with:
```bash
python3 -m unittest discover tests
```
