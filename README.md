# Solid-Principles

The SOLID principles are a valuable set of guidelines for writing better code. By following these principles, you can write code that is easier to understand, maintain, and extend.
In Python programming, "solid principles" typically refer to the SOLID principles, which are a set of five design principles that help you create maintainable and scalable software. These

principles were introduced by Robert C. Martin and are commonly used in object-oriented programming. The SOLID acronym stands for:

**Single Responsibility Principle (SRP)**: This principle states that a class should have only one reason to change. In other words, a class should have only one responsibility or job. This promotes modular and maintainable code.
A class should have only one responsibility. This means that each class should only do one thing and do it well.

So, what does that mean actually? While you design your logic in either class or method, _**you should not be writing all kinds of responsibilities in one place**_. This will make your code quite complex and unmanageable. It will also be difficult to adjust new changes later as there are high chances it will affect the other functionality and you will end up testing all the functionalities even though it is a smaller change.

# Single Responsibility Principle (SRP)

class FileManager:
    def __init__(self, file_path):
        self.file_path = file_path

    def read_file(self):
        pass

    def write_file(self, data):
        pass

    def encrypt_data(self, data):
        pass

    def decrypt_data(self, data):
        pass

In this example, the `FileManager` class violates SRP because it has multiple responsibilities. It is responsible for file management operations such as reading and writing files, as well as performing encryption and decryption of data.
To apply SRP, we can separate the responsibilities into different classes:

class FileManager
    def __init__(self, file_path):
        self.file_path = file_path

    def read_file(self):
        pass

    def write_file(self, data):
        pass

class DataEncryptor:
    def encrypt_data(self, data):
        pass

    def decrypt_data(self, data):
        pass

In this refactored version, the `FileManager` class now focuses solely on file management operations. It handles reading and writing data to/from a file. On the other hand, the `DataEncryptor` class is responsible for encrypting and decrypting data.

**Open-Closed Principle (OCP)**: According to the OCP, software entities (classes, modules, functions, etc.) should be open for extension but closed for modification. You should be able to add new functionality without changing existing code.
It means that we should be able to add new functionality to the code without having to modify existing classes. By including new features without the need to change existing code, we can reduce bugs.

![image](https://github.com/developer-Akhil/Solid-Principles/assets/64408106/34543303-34c2-4f51-a50c-18f850bc3c94)

class Person:
    def __init__(self, name):
        self.name = name

    def __repr__(self):
        return f'Person(name={self.name})'

class PersonStorage:
    def save_to_database(self, person):
        print(f'Save the {person} to database')

    def save_to_json(self, person):
        print(f'Save the {person} to a JSON file')

if __name__ == '__main__':
    person = Person('John Doe')
    storage = PersonStorage()
    storage.save_to_database(person)
    
The open-closed principle example

![image](https://github.com/developer-Akhil/Solid-Principles/assets/64408106/a150062b-9e4e-4c29-abaf-ca66d0830637)
