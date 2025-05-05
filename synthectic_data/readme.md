# Synthetic Testing Data Generator

A powerful tool for generating realistic synthetic test data using OPENAI model.

## Features

- Generate high-quality synthetic data based on custom schemas
- Support for various data types and relationships
- Configurable constraints and distributions
- Multiple output formats (JSON, CSV, SQLite)
- Easy to extend and customize

### Schema Structure

- **name**: Name of the dataset
- **description**: Description of the dataset
- **fields**: Array of field definitions
  - **name**: Field name
  - **type**: Data type (string, integer, date, enum, etc.)
  - **description**: Field description
  - Additional type-specific properties (min, max, format, values, etc.)
- **constraints**: Array of constraints as natural language instructions
- **additional_instructions**: Special instructions for data generation

## Creating Schemas

Schemas are defined in JSON format. Here's an example:

```json
{
  "name": "Users Test Dataset",
  "description": "Synthetic user data for application testing",
  "fields": [
    {
      "name": "id",
      "type": "uuid",
      "description": "Unique identifier for each user"
    },
    {
      "name": "first_name",
      "type": "string",
      "description": "User's first name"
    },
    {
      "name": "last_name",
      "type": "string",
      "description": "User's last name"
    }
    // Additional fields...
  ],
  "constraints": [
    "If age is under 25, subscription_tier should be more likely to be 'free' or 'basic'",
    "80% of users should have is_active set to true"
  ],
  "additional_instructions": "Create diverse, realistic users with varied cultural backgrounds."
}
```
