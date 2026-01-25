# WordMaster Marketplace

This directory contains shared vocabulary books that users can download and import into their WordMaster application.

## Repository Structure

- `index.json`: The main registry file listing all available books.
- `wordbook/`: Directory containing the actual JSON data files for each vocabulary book.
- `README.md`: This documentation file.

## How to Add New Books

To contribute a new vocabulary book to the Marketplace:

1.  **Create the Book Data File**:
    - Create a new JSON file in the `wordbook/` directory (e.g., `wordbook/my_new_book.json`).
    - Follow the [JSON Schema](#json-schema) below for the file content.

2.  **Update the Registry**:
    - Edit `index.json`.
    - Add a new entry to the `book` array pointing to your new file.

    Example entry:
    ```json
    {
      "name": "My New Book Name",
      "description": "A brief description of the vocabulary content.",
      "path": "wordbook/my_new_book.json"
    }
    ```

## JSON Schema

### Wordbook File Format
The wordbook JSON file should follow this structure:

```json
{
  "name": "Book Title",
  "description": "Book Description",
  "words": [
    {
      "word": "example",
      "chinese": "n. 例子",
      "phonetic": "/ɪɡˈzæmpəl/",
      "part_of_speech": "noun",
      "sentences": [
        "This is a good example.",
        "For example, you can do this."
      ]
    }
  ]
}
```

### Word Entry Details

Each object in the `words` array represents a vocabulary item:

- **word** (string, required): The English word.
- **chinese** (string, required): The Chinese definition/translation.
- **phonetic** (string, optional): The IPA phonetic transcription.
- **part_of_speech** (string, optional): The grammatical category (e.g., "noun", "verb", "adj").
- **sentences** (array of strings, optional): Example sentences using the word.
