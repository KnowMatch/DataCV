# DataCV

Why not OpenCV? OpenCV was taken
```
resume_specification:
  version: IN_DEV
  descgithbription: "Abstract specification for resume data format in YAML, allowing for extensible and customizable fields."

fields:
  personal_info:
    required: true
    type: object
    description: "Personal contact information and identifiers. Designed to be extensible with custom fields."
    properties:
      name:
        required: true
        type: string
        description: "Full name of the individual."
      contact_methods:
        required: true
        type: array
        description: "List of methods to contact the individual, including type and value. Allows for extensibility."
        items:
          type: object
          properties:
            type:
              required: true
              type: string
              description: "Type of contact method (e.g., email, phone, social)."
            value:
              required: true
              type: string
              description: "Value of the contact method, could be an email address, phone number, or URL."

  objective:
    required: false
    type: string
    description: "Brief statement of career objectives."

  education:
    required: true
    type: array
    description: "Educational background. Allows for multiple entries."
    items:
      type: object
      properties:
        institution:
          required: true
          type: string
          description: "Name of the educational institution."
        degree:
          required: true
          type: string
          description: "Degree or certification obtained."
        field_of_study:
          required: false
          type: string
          description: "The field or major of study."
        start_date:
          required: true
          type: string
          format: date
          description: "Start date of the education period."
        end_date:
          required: false
          type: string
          format: date
          description: "End date of the education period. Omit if current."
        achievements:
          required: false
          type: array
          description: "List of achievements or honors received during the education period."
          items:
            type: string
```
