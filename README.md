**🚀 Smart Flashcard System – FastAPI Backend**
An intelligent backend API built with FastAPI that powers a smart flashcard system. It allows students to create flashcards without specifying subjects — our system infers the subject based on the question content and helps students revise efficiently with subject-wise mixed flashcards.


**🔧 Tech Stack**
🌐 FastAPI – Lightweight, fast web framework for building APIs

🧠 Rule-Based Subject Inference – Simple keyword-matching logic

🗂️ Custom Python Storage – Stores flashcards in memory (can be extended to database)


**✨ Features**
➕ Add flashcards with only a question and answer

🧠 Automatically detects the subject (Physics, Biology, etc.)

🔄 Retrieve shuffled flashcards from different subjects

👨‍🎓 Filter flashcards by student_id

⚡ Super fast and interactive API with Swagger UI


**📦 Installation**
bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>

**✅ Setup Virtual Environment (Optional)**
bash
python -m venv venv
source venv/bin/activate       # Windows: venv\Scripts\activate

**🛠 Install Dependencies**
bash
pip install fastapi uvicorn


**🔌 API Endpoints**
1. POST /flashcard
➡️ Adds a flashcard with automatic subject detection.


Request
json
{
  "student_id": "stu001",
  "question": "What is Newton's Second Law?",
  "answer": "Force equals mass times acceleration"
}
Response
json
{
  "message": "Flashcard added successfully",
  "subject": "Physics"
}

2. GET /get-subject?student_id=stu001&limit=5
➡️ Returns a shuffled list of flashcards from different subjects for the student.

Response
json
[
  {
    "question": "What is Newton's Second Law?",
    "answer": "Force equals mass times acceleration",
    "subject": "Physics"
  },
  {
    "question": "What is photosynthesis?",
    "answer": "A process used by plants to convert light into energy",
    "subject": "Biology"
  }
]


**🧠 How Subject Inference Works**
This system uses a simple rule-based classifier in subject_classifier.py. Based on specific keywords in the question text, it assigns a subject like:

Keyword(s)	Inferred Subject
force, motion, gravity	Physics
cell, photosynthesis	Biology
triangle, equation	Mathematics

🔍 Can easily extend this to use ML/NLP models or external APIs.


**📁 Project Structure**
bash
.
├── main.py                  # FastAPI endpoints
├── subject_classifier.py    # Logic for subject detection
├── storage.py               # In-memory flashcard storage
├── README.md


**✅ Submission Checklist**

 Public GitHub repo with complete working code

 Readable, well-structured code

 README with setup + usage instructions

 API tested on Swagger docs

 Link submitted in the Google Form
