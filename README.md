

# Language Detector

This Python project detects the language of a given text and provides the full language name using the `langdetect` and `langcodes` libraries.

## Features

- Detects the language of the input text.
- Converts the detected language code into the full language name.
- Supports detection of multiple languages (e.g., English, French, Spanish).

## Requirements

- Python 3.x
- `langdetect` library
- `langcodes` library

### Install Required Libraries

To install the necessary libraries, run the following commands:

```bash
!pip install langdetect
!pip install langcodes
```

## Usage

1. **Clone or Download** the repository.
2. Run the script using the following Python code:

```python
# Importing the necessary libraries
from langdetect import detect  # To detect the language code from text
import langcodes  # To convert the detected language code into a full language name

# Prompt the user to input text for language detection
text = input("Enter the text word that u need:")  # Taking input text from the user

# Detect the language of the input text using langdetect
lang_code = detect(text)  # This returns the detected language code (e.g., 'en' for English)

# Convert the language code to its full name using langcodes
lang_name = langcodes.get(lang_code).display_name()  # Converts 'en' to 'English'

# Print the detected language name
print(lang_name)  # Display the full name of the detected language
```

### Example Usage

#### Example 1: English Text

```bash
Enter the text word that u need: Hello, how are you?
English
```

#### Example 2: Spanish Text

```bash
Enter the text word that u need: Hola, ¿cómo estás?
Spanish
```

#### Example 3: French Text

```bash
Enter the text word that u need: Bonjour, comment ça va?
French
```

### How It Works

- The script takes user input for a word or sentence.
- The input text is processed by the `langdetect` library, which returns the **language code** (e.g., 'en', 'fr', 'es').
- The language code is then passed to the `langcodes` library to get the **full language name** (e.g., 'English', 'French', 'Spanish').
- Finally, the detected language name is displayed to the user.

### Supported Languages

The `langdetect` library supports over 50 languages. Some of the common ones include:

- **en** – English
- **fr** – French
- **es** – Spanish
- **de** – German
- **it** – Italian
- **pt** – Portuguese
- **ru** – Russian
- **ar** – Arabic
- **zh** – Chinese (Simplified)

### Handling Exceptions

In case the language cannot be detected or if the text is too short, you can enhance the script by adding exception handling:

```python
from langdetect import detect, LangDetectException
import langcodes

# Taking input text
text = input("Enter the text word that u need:")

try:
    # Detect the language of the input text
    lang_code = detect(text)

    # Convert the language code to the full name
    lang_name = langcodes.get(lang_code).display_name()
    print(f"The detected language is: {lang_name}")

except LangDetectException:
    print("Sorry, the language could not be detected.")
```

This would help handle cases where the language cannot be reliably detected.
