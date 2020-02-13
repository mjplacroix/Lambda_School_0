### OOP, Code Style, and Reviews

Lambda Materials:
  + https://learn.lambdaschool.com/ds/module/recqeF16aJfb1UTWF/
  + https://github.com/LambdaSchool/DS-Unit-3-Sprint-1-Software-Engineering/tree/master/module2-oop-code-style-and-reviews
  
Style, Formatting, and PEP8:
  + https://pep8.org/
  + https://pypi.org/project/autopep8/
  
Docs / Docstrings:
  + https://readthedocs.org/
  + https://docs.readthedocs.io/en/stable/intro/getting-started-with-sphinx.html
  
(BONUS) Doc generation in the wild (Pandas):
  + https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html
  + https://github.com/pandas-dev/pandas/blob/master/pandas/core/frame.py#L319
  
(BONUS) Classes - examples of class method decorators:
  + https://realpython.com/instance-class-and-static-methods-demystified/#static-methods

(BONUS) Inheritance Example in the wild (SKLearn):
  + https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/tree/_classes.py#L77
  + https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/tree/_classes.py#L589

(BONUS) Refactoring from Functions to Classes in the wild (s2t2's Playlist Service):
  + https://github.com/s2t2/playlist-service-py/blob/25cae16201adc935f71e863a79d51690c00e492b/app/spotify_service.py
  + https://github.com/s2t2/playlist-service-py/blob/master/app/spotify_service.py

(BONUS) Importing Classes in the wild (s2t2's Playlist Service):
  + https://github.com/s2t2/playlist-service-py/blob/master/app/sync_service.py

### Links from Class

PEP Docstring Conventions
  + https://www.python.org/dev/peps/pep-0257/
  
Starter code for working with classes:
```python
def full_name(team):
    return f"{team['city']} {team['name']}"
def advertise(team):
    print(f"HELLO PLEASE COME TO {team['city']} TO SEE OUR GAMES!")
if __name__ == "__main__":
    teams = [
        {"city": "New York", "name": "Yankees"},
        {"city": "New York", "name": "Mets"},
        {"city": "Boston", "name": "Red Sox"},
        {"city": "New Haven", "name": "Ravens"}
    ]
    for team in teams:
        print("---------")
        print(full_name(team))
        advertise(team)
```

Next steps:
```python
class Team(object):
    def __init__(self, city, name):
        self.name = name
        self.city = city
def full_name(team):
    """Param team dict with keys of city and name"""
    return f"{team['city']} {team['name']}"
def advertise(team):
    """Param team dict with keys of city and name"""
    print(f"HELLO PLEASE COME TO {team['city'].upper()} TO SEE OUR GAMES!")
if __name__ == "__main__":
    team = Team(city="Washington DC", name="Warriors")
    print(team)
    print(type(team))
    print(dir(team))
    print(team.name)
    #teams = [
    #    {"city": "New York", "name": "Yankees"},
    #    {"city": "New York", "name": "Mets"},
    #    {"city": "Boston", "name": "Red Sox"},
    #    {"city": "New Haven", "name": "Ravens"}
    #]
    #for team in teams:
    #    print("---------")
    #    print(full_name(team))
    #    advertise(team)
```

Using property decorator:
```python
class Team(object):
    def __init__(self, city, name):
        self.name = name
        self.city = city
    @property
    def full_name(self):
        return f"{self.city} {self.name}"
def advertise(team):
    """Param team dict with keys of city and name"""
    print(f"HELLO PLEASE COME TO {team['city'].upper()} TO SEE OUR GAMES!")
if __name__ == "__main__":
    team = Team(city="Washington DC", name="Warriors")
    print(team)
    print(type(team))
    print(dir(team))
    print(team.name)
    print(team.full_name)
    #print(team.full_name())
    #teams = [
    #    {"city": "New York", "name": "Yankees"},
    #    {"city": "New York", "name": "Mets"},
    #    {"city": "Boston", "name": "Red Sox"},
    #    {"city": "New Haven", "name": "Ravens"}
    #]
    #for team in teams:
    #    print("---------")
    #    print(full_name(team))
    #    advertise(team)
``` 
