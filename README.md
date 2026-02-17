# Game Character Stats Tracker - OOP

## Overview
A simple Object-Oriented Python implementation of a game character class that tracks character stats including health, mana, name, and level with built-in validation.

## Class: GameCharacter

### Description
Represents a game character with core attributes and mechanics for managing character progression and resource management.

### Attributes

#### Private Attributes
- `_name` (str): The character's name
- `_health` (int): Current health points (0-100, default: 100)
- `_mana` (int): Current magic points (0-50, default: 50)
- `_level` (int): Current character level (default: 1)

### Properties

#### `name` (Read-only)
Returns the character's name.

```python
character.name  # Returns: "Archer"
```

#### `health` (Read/Write)
Gets or sets the character's health with automatic validation:
- Values below 0 are set to 0
- Values above 100 are capped at 100
- Valid values are stored as-is

```python
character.health = 50  # Valid
character.health = 150  # Capped to 100
character.health = -10  # Set to 0
```

#### `mana` (Read/Write)
Gets or sets the character's mana with automatic validation:
- Values below 0 are set to 0
- Values above 50 are capped at 50
- Valid values are stored as-is

```python
character.mana = 25  # Valid
character.mana = 100  # Capped to 50
character.mana = -5  # Set to 0
```

#### `level` (Read-only)
Returns the character's current level.

```python
character.level  # Returns: 1
```

### Methods

#### `__init__(name)`
Initializes a new character with default stats.

**Parameters:**
- `name` (str): The character's name

**Example:**
```python
hero = GameCharacter("Archer")
```

#### `level_up()`
Increases character level by 1 and restores health and mana to maximum values. Prints a level-up message.

**Example:**
```python
hero.level_up()
# Output: Archer has leveled up to level 2!
```

#### `__str__()`
Returns a formatted string representation of the character's stats.

**Example:**
```python
print(hero)
# Output:
# Name: Archer
# Level: 1
# Health: 100
# Mana: 50
```

## Usage Example

```python
# Create a new character
hero = GameCharacter("Archer")
print(hero)

# Damage the character
hero.health -= 20
hero.mana -= 10
print(hero)

# Level up
hero.level_up()
print(hero)
```

**Output:**
```
Name: Archer
Level: 1
Health: 100
Mana: 50

Name: Archer
Level: 1
Health: 80
Mana: 40

Archer has leveled up to level 2!
Name: Archer
Level: 2
Health: 100
Mana: 50
```

## Key Features

- **Encapsulation**: Uses private attributes to protect data integrity
- **Property Decorators**: Implements getters and setters with validation
- **Data Validation**: Health and mana are automatically constrained within valid ranges
- **Character Progression**: Level system with stat restoration on level-up
- **String Representation**: User-friendly display of character stats
