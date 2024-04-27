# AirBnB Clone Project - Version 3

## Introduction
This is the 3rd version of our AirBnB clone project. We will be using a REST API and Flask.

## Table of Contents
- [Environment](#environment)
- [Installation](#installation)
- [File Descriptions](#file-descriptions)
- [Usage](#usage)
- [Examples of Use](#examples-of-use)
- [Bugs](#bugs)
- [Authors](#authors)
- [License](#license)

## Environment
This project is interpreted/tested on Ubuntu 14.04 LTS using python3 (version 3.4.3).

## Installation
- Run hbnb(interactively): `./console` and enter command.
- Run hbnb(non-interactively): `echo "<command>" | ./console.py`.

## File Descriptions
- `console.py`: The console contains the entry point of the command interpreter. List of commands this console currently supports:
    - `EOF`: Exits console.
    - `quit`: Exits console.
    - `<emptyline>`: Overwrites default emptyline method and does nothing.
    - `create`: Creates a new instance of BaseModel, saves it (to the JSON file), and prints the id.
    - `destroy`: Deletes an instance based on the class name and id (save the change into the JSON file).
    - `show`: Prints the string representation of an instance based on the class name and id.
    - `all`: Prints all string representations of all instances based or not on the class name.
    - `update`: Updates an instance based on the class name and id by adding or updating attribute (save the change into the JSON file).

- `models/` directory contains classes used for this project:
    - `base_model.py`: The BaseModel class from which future classes will be derived.
        - `__init__(self, *args, **kwargs)`: Initialization of the base model.
        - `__str__(self)`: String representation of the BaseModel class.
        - `save(self)`: Updates the attribute updated_at with the current datetime.
        - `to_dict(self)`: Returns a dictionary containing all keys/values of the instance.

- Classes inherited from BaseModel:
    - `amenity.py`
    - `city.py`
    - `place.py`
    - `review.py`
    - `state.py`
    - `user.py`

- `/models/engine` directory contains File Storage class that handles JSON serialization and deserialization:
    - `file_storage.py`: Serializes instances to a JSON file & deserializes back to instances.
        - `all(self)`: Returns the dictionary __objects.
        - `new(self, obj)`: Sets in __objects the obj with key .id.
        - `save(self)`: Serializes __objects to the JSON file (path: __file_path).
        - `reload(self)`: Deserializes the JSON file to __objects.

- `/tests` directory contains all unit test cases for this project:
    - `/test_models/test_base_model.py`: Contains the TestBaseModel and TestBaseModelDocs classes.
        - `TestBaseModelDocs` class:
            - `setUpClass(cls)`: Set up for the doc tests.
            - `test_pep8_conformance_base_model(self)`: Test that models/base_model.py conforms to PEP8.
            - `test_pep8_conformance_test_base_model(self)`: Test that tests/test_models/test_base_model.py conforms to PEP8.
            - `test_bm_module_docstring(self)`: Test for the base_model.py module docstring.
            - `test_bm_class_docstring(self)`: Test for the BaseModel class docstring.
            - `test_bm_func_docstrings(self)`: Test for the presence of docstrings in BaseModel methods.

        - `TestBaseModel` class:
            - `test_is_base_model(self)`: Test that the instantiation of a BaseModel works.
            - `test_created_at_instantiation(self)`: Test created_at is a public instance attribute of type datetime.
            - `test_updated_at_instantiation(self)`: Test updated_at is a public instance attribute of type datetime.
            - `test_diff_datetime_objs(self)`: Test that two BaseModel instances have different datetime objects.

    - `/test_models/test_amenity.py`: Contains the TestAmenityDocs class.
    - `/test_models/test_city.py`: Contains the TestCityDocs class.
    - `/test_models/test_file_storage.py`: Contains the TestFileStorageDocs class.
    - `/test_models/test_place.py`: Contains the TestPlaceDoc class.
    - `/test_models/test_review.py`: Contains the TestReviewDocs class.
    - `/test_models/state.py`: Contains the TestStateDocs class.
    - `/test_models/user.py`: Contains the TestUserDocs class.

## Usage
To use this project, follow the installation instructions mentioned above. Once installed, you can interact with the command-line interface using the supported commands.

## Examples of Use
- Creating a new instance:
    ```
    create BaseModel
    ```

- Showing an instance:
    ```
    show BaseModel 1234-5678-9012
    ```

- Updating an instance:
    ```
    update BaseModel 1234-5678-9012 name "New Name"
    ```

## Bugs
No known bugs at the moment. If you encounter any issues, please report them [here](https://github.com/your-repo-name/issues).

## Authors
- [Author 1] Yves IRAKOZE MFURA
- [Author 2] Leonce TWAYINGANYIKI
