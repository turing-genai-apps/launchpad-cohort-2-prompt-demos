# Named Entity Extraction Template

## Prompt

You are an expert in information extraction and natural language processing, specializing in identifying and extracting structured personal information from unstructured text. I need you to analyze the provided text and extract specific personal identification details in a structured JSON format.

Please extract the following information:
1. Full Name (including any middle names if present)
2. Gender
3. Date of Birth (in YYYY-MM-DD format)
4. Passport Number

Requirements for extraction:

1. Format all extracted information in a clean JSON structure
2. Maintain data accuracy - if a field cannot be determined with certainty, mark it as null
3. For dates, standardize to ISO format (YYYY-MM-DD)
4. For passport numbers, preserve exact formatting as found in the text
5. Handle missing information gracefully by including the field with a null value
6. If multiple possible values are found, include only the most confident match

Expected JSON Structure:
```json
{
    "full_name": string | null,
    "gender": string | null,
    "date_of_birth": string | null,
    "passport_number": string | null
}
```

Here are the details:
```
भारत गणराज्य / REPUBLIC OF INDIA

Type: P
Country Code: IND
Passport No.: J8369854

Surname: RAMADUGULA
Given Name(s): SITA MAHA LAKSHMI
Nationality: INDIAN
Sex: F
Date of Birth: 23/09/1959
Place of Birth: GUNDUGOLANU
Place of Issue: HYDERABAD
Date of Issue: 11/10/2011
Date of Expiry: 10/10/2021

(Signature)
R.S. Lakshmi
```

## LLM Response

Based on the provided text, here is the extracted personal identification information in the requested JSON format:



```json
{
    "full_name": "Sita Maha Lakshmi Ramadugula",
    "gender": "Female",
    "date_of_birth": "1959-09-23",
    "passport_number": "J8369854"
}
```

Explanation:

 - **Full Name:** Combined the given name ("SITA MAHA LAKSHMI") with the surname ("RAMADUGULA") in natural order.

 - **Gender:** "Sex: F" corresponds to "Female".

 - **Date of Birth:** Reformatted from "23/09/1959" to "1959-09-23" (ISO format).

 - **Passport Number:** Extracted exactly as written: "J8369854".

Let me know if you'd like this process automated for multiple entries or in another format.
