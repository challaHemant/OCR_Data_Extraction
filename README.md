# OCR_Data_Extraction
A Python-based OCR project for extracting and structuring text data from patient assessment forms.
# 📝 OCR Data Extraction Project  
> A Python-based OCR solution for extracting structured data from patient assessment forms.

## 📌 Overview  
This project uses **Tesseract OCR** to extract handwritten and printed text from patient assessment forms. The extracted data is structured and stored in a **PostgreSQL** database for further analysis and retrieval.

## 🚀 Features  
✅ Extracts key data points like patient details, treatment info, difficulty ratings, pain symptoms, and medical assistant inputs.  
✅ Supports **preprocessing techniques** (binarization, noise removal, deskewing) to improve OCR accuracy.  
✅ Stores extracted data in a **PostgreSQL database** in structured JSON format.  
✅ Includes **error handling and data validation** to ensure reliable extraction.  

## 🏗️ Project Structure  
OCR_Data_Extraction/ │── OCR_script.ipynb # Jupyter Notebook for OCR text extraction │── db_insert.py # Script to insert extracted data into PostgreSQL │── db_schema.sql # Database schema for PostgreSQL │── requirements.txt # List of dependencies │── sample_forms/ # Example scanned forms (images) │── extracted_output/ # Folder for extracted JSON data │── README.md # Project documentation

bash
Copy
Edit

## 🛠️ Setup Instructions  

### 1️⃣ **Clone the Repository**  
```bash
git clone https://github.com/hemanthchalla/OCR_Data_Extraction.git
cd OCR_Data_Extraction
2️⃣ Install Dependencies
bash
Copy
Edit
pip install -r requirements.txt
3️⃣ Setup PostgreSQL Database
Ensure PostgreSQL is installed and running.
Create a database:
sql
Copy
Edit
CREATE DATABASE ocr_db;
Run the schema file to create required tables:
bash
Copy
Edit
psql -U your_username -d ocr_db -f db_schema.sql
4️⃣ Run OCR Extraction
Execute the Jupyter Notebook OCR_script.ipynb to extract text from patient forms.

5️⃣ Store Extracted Data
Run the following script to insert extracted data into the database:

bash
Copy
Edit
python db_insert.py
📊 Database Schema
The project stores extracted data in PostgreSQL with the following tables:

patients (patient_id, name, dob, assessment_date)
treatments (patient_id, injection, exercise_therapy)
difficulty_ratings (patient_id, bending, putting_on_shoes, etc.)
pain_symptoms (patient_id, pain, numbness, tingling, etc.)
patient_changes (patient_id, since_last_treatment, last_3_days)
medical_assistant_data (patient_id, blood_pressure, hr, weight, etc.)
📝 Example JSON Output
json
Copy
Edit
{
  "patient_name": "John Doe",
  "dob": "1985-06-15",
  "assessment_date": "2024-02-10",
  "treatments": { "injection": "Yes", "exercise_therapy": "No" },
  "difficulty_ratings": { "bending": 2, "stairs": 4 },
  "pain_symptoms": { "pain": 3, "numbness": 1 },
  "medical_assistant_data": { "blood_pressure": "120/80", "hr": 72 }
}
📌 Future Improvements
🔹 Enhance OCR accuracy with deep learning-based handwriting recognition
🔹 Implement a web-based UI for form uploads and result visualization
🔹 Add API endpoints for data retrieval

📜 License
This project is licensed under the MIT License. Feel free to use and modify it!

🔗 GitHub: hemanthchalla
