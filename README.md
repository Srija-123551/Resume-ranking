# Resume-ranking
{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 1,
   "id": "151f9fac-6c8f-4e3b-84e1-52f590188d43",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Collecting PyPDF2\n",
      "  Downloading pypdf2-3.0.1-py3-none-any.whl (232 kB)\n",
      "Collecting typing_extensions>=3.10.0.0; python_version < \"3.10\"\n",
      "  Downloading typing_extensions-4.12.2-py3-none-any.whl (37 kB)\n",
      "Installing collected packages: typing-extensions, PyPDF2\n",
      "Successfully installed PyPDF2-3.0.1 typing-extensions-4.12.2\n"
     ]
    },
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "WARNING: You are using pip version 20.1.1; however, version 25.0.1 is available.\n",
      "You should consider upgrading via the 'c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\python.exe -m pip install --upgrade pip' command.\n"
     ]
    }
   ],
   "source": [
    "!pip install PyPDF2"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "id": "9e0da60f-7b64-4fb1-848b-378649c030eb",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Requirement already satisfied: scikit-learn in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (1.3.2)\n",
      "Requirement already satisfied: threadpoolctl>=2.0.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from scikit-learn) (3.5.0)\n",
      "Requirement already satisfied: joblib>=1.1.1 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from scikit-learn) (1.4.2)\n",
      "Requirement already satisfied: numpy<2.0,>=1.17.3 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from scikit-learn) (1.24.4)\n",
      "Requirement already satisfied: scipy>=1.5.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from scikit-learn) (1.10.1)\n"
     ]
    },
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "WARNING: You are using pip version 20.1.1; however, version 25.0.1 is available.\n",
      "You should consider upgrading via the 'c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\python.exe -m pip install --upgrade pip' command.\n"
     ]
    }
   ],
   "source": [
    "!pip install scikit-learn"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "id": "e24137a9-fe5a-42a4-87a7-cbcb0f2c0371",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Requirement already satisfied: streamlit in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (1.40.1)\n",
      "Requirement already satisfied: packaging<25,>=20 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (24.2)\n",
      "Requirement already satisfied: pandas<3,>=1.4.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (2.0.3)\n",
      "Requirement already satisfied: gitpython!=3.1.19,<4,>=3.0.7 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (3.1.44)\n",
      "Requirement already satisfied: watchdog<7,>=2.1.5; platform_system != \"Darwin\" in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (4.0.2)\n",
      "Requirement already satisfied: tornado<7,>=6.0.3 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (6.4.2)\n",
      "Requirement already satisfied: numpy<3,>=1.20 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (1.24.4)\n",
      "Requirement already satisfied: pyarrow>=7.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (17.0.0)\n",
      "Requirement already satisfied: requests<3,>=2.27 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (2.32.3)\n",
      "Requirement already satisfied: click<9,>=7.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (8.1.8)\n",
      "Requirement already satisfied: blinker<2,>=1.0.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (1.8.2)\n",
      "Requirement already satisfied: toml<2,>=0.10.1 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (0.10.2)\n",
      "Requirement already satisfied: pillow<12,>=7.1.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (10.4.0)\n",
      "Requirement already satisfied: altair<6,>=4.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (5.4.1)\n",
      "Requirement already satisfied: cachetools<6,>=4.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (5.5.2)\n",
      "Requirement already satisfied: tenacity<10,>=8.1.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (9.0.0)\n",
      "Requirement already satisfied: typing-extensions<5,>=4.3.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (4.12.2)\n",
      "Requirement already satisfied: pydeck<1,>=0.8.0b4 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (0.9.1)\n",
      "Requirement already satisfied: rich<14,>=10.14.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (13.9.4)\n",
      "Requirement already satisfied: protobuf<6,>=3.20 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from streamlit) (5.29.3)\n",
      "Requirement already satisfied: python-dateutil>=2.8.2 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from pandas<3,>=1.4.0->streamlit) (2.9.0.post0)\n",
      "Requirement already satisfied: tzdata>=2022.1 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from pandas<3,>=1.4.0->streamlit) (2025.1)\n",
      "Requirement already satisfied: pytz>=2020.1 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from pandas<3,>=1.4.0->streamlit) (2025.1)\n",
      "Requirement already satisfied: gitdb<5,>=4.0.1 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from gitpython!=3.1.19,<4,>=3.0.7->streamlit) (4.0.12)\n",
      "Requirement already satisfied: charset-normalizer<4,>=2 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from requests<3,>=2.27->streamlit) (3.4.1)\n",
      "Requirement already satisfied: idna<4,>=2.5 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from requests<3,>=2.27->streamlit) (3.10)\n",
      "Requirement already satisfied: certifi>=2017.4.17 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from requests<3,>=2.27->streamlit) (2025.1.31)\n",
      "Requirement already satisfied: urllib3<3,>=1.21.1 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from requests<3,>=2.27->streamlit) (2.2.3)\n",
      "Requirement already satisfied: colorama; platform_system == \"Windows\" in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from click<9,>=7.0->streamlit) (0.4.6)\n",
      "Requirement already satisfied: narwhals>=1.5.2 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from altair<6,>=4.0->streamlit) (1.29.0)\n",
      "Requirement already satisfied: jinja2 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from altair<6,>=4.0->streamlit) (3.1.5)\n",
      "Requirement already satisfied: jsonschema>=3.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from altair<6,>=4.0->streamlit) (4.23.0)\n",
      "Requirement already satisfied: pygments<3.0.0,>=2.13.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from rich<14,>=10.14.0->streamlit) (2.19.1)\n",
      "Requirement already satisfied: markdown-it-py>=2.2.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from rich<14,>=10.14.0->streamlit) (3.0.0)\n",
      "Requirement already satisfied: six>=1.5 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from python-dateutil>=2.8.2->pandas<3,>=1.4.0->streamlit) (1.17.0)\n",
      "Requirement already satisfied: smmap<6,>=3.0.1 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from gitdb<5,>=4.0.1->gitpython!=3.1.19,<4,>=3.0.7->streamlit) (5.0.2)\n",
      "Requirement already satisfied: MarkupSafe>=2.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from jinja2->altair<6,>=4.0->streamlit) (2.1.5)\n",
      "Requirement already satisfied: importlib-resources>=1.4.0; python_version < \"3.9\" in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from jsonschema>=3.0->altair<6,>=4.0->streamlit) (6.4.5)\n",
      "Requirement already satisfied: pkgutil-resolve-name>=1.3.10; python_version < \"3.9\" in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from jsonschema>=3.0->altair<6,>=4.0->streamlit) (1.3.10)\n",
      "Requirement already satisfied: jsonschema-specifications>=2023.03.6 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from jsonschema>=3.0->altair<6,>=4.0->streamlit) (2023.12.1)\n",
      "Requirement already satisfied: referencing>=0.28.4 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from jsonschema>=3.0->altair<6,>=4.0->streamlit) (0.35.1)\n",
      "Requirement already satisfied: rpds-py>=0.7.1 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from jsonschema>=3.0->altair<6,>=4.0->streamlit) (0.20.1)\n",
      "Requirement already satisfied: attrs>=22.2.0 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from jsonschema>=3.0->altair<6,>=4.0->streamlit) (25.1.0)\n",
      "Requirement already satisfied: mdurl~=0.1 in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from markdown-it-py>=2.2.0->rich<14,>=10.14.0->streamlit) (0.1.2)\n",
      "Requirement already satisfied: zipp>=3.1.0; python_version < \"3.10\" in c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\lib\\site-packages (from importlib-resources>=1.4.0; python_version < \"3.9\"->jsonschema>=3.0->altair<6,>=4.0->streamlit) (3.20.2)\n"
     ]
    },
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "WARNING: You are using pip version 20.1.1; however, version 25.0.1 is available.\n",
      "You should consider upgrading via the 'c:\\users\\dell\\appdata\\local\\programs\\python\\python38\\python.exe -m pip install --upgrade pip' command.\n"
     ]
    }
   ],
   "source": [
    "!pip install streamlit"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1,
   "id": "9f0dfeef-9144-4fa5-aa3f-65fa3f0e3d7b",
   "metadata": {},
   "outputs": [],
   "source": [
    "import streamlit as st\n",
    "from PyPDF2 import PdfReader\n",
    "import pandas as pd\n",
    "from sklearn.feature_extraction.text import TfidfVectorizer\n",
    "from sklearn.metrics.pairwise import cosine_similarity"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "id": "adeaac88-5c56-4971-bb3f-59c4bbb60c4a",
   "metadata": {},
   "outputs": [],
   "source": [
    "# Function to extract text from PDF\n",
    "def extract_text_from_pdf(file):\n",
    "    pdf = PdfReader(file)\n",
    "    text = \"\"\n",
    "    for page in pdf.pages:\n",
    "        text += page.extract_text()\n",
    "    return text"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "5346adba-c7be-43e0-8962-c8ea95db7c18",
   "metadata": {},
   "outputs": [],
   "source": [
    "# Function to rank resumes based on job description\n",
    "def rank_resumes(job_description, resumes):\n",
    "    # Combine job description with resumes\n",
    "    documents= [job_description] + resumes\n",
    "    vectorizer = TfidfVectorizer().fit_transform(documents)\n",
    "    vectors= vectorizer.toarray()\n",
    "\n",
    "    # Calculate cosine similarity\n",
    "    job_description_vector = vectors[0]\n",
    "    resume_vectors = vectors [1:]\n",
    "    cosine_similarities = cosine_similarity ([job_description_vector], resume_vectors).flatten()\n",
    "    \n",
    "    return cosine_similarities"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "fe4f6753-d769-43c4-891a-4874d57ebdf6",
   "metadata": {},
   "outputs": [],
   "source": [
    "# Streamlit app\n",
    "st.title(\"AI Resume Screening & Candidate Ranking System\")\n",
    "# Job description input\n",
    "st.header(\"Job Description\")\n",
    "job_description= st.text_area (\"Enter the job description\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "8b4202d6-4e09-4119-b1fd-9adb991b4ab5",
   "metadata": {},
   "outputs": [],
   "source": [
    "# File uploader\n",
    "st.header(\"Upload Resumes\")\n",
    "uploaded_files = st.file_uploader(\"Upload PDF files\", type=[\"pdf\"], accept_multiple_files=True)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "8e218fd3-19a8-4514-98bb-e5d6672df465",
   "metadata": {},
   "outputs": [],
   "source": [
    "if uploaded_files and job_description:\n",
    "    st.header(\"Ranking Resumes\")\n",
    "    \n",
    "    resumes = []\n",
    "    for file in uploaded_files:\n",
    "        text = extract_text_from_pdf(file)\n",
    "        resumes.append(text)\n",
    "\n",
    "    # Rank resumes\n",
    "    score = rank_resumes(job_description, resumes)\n",
    "\n",
    "    # Display scores\n",
    "    results = pd.DataFrame({\"Resume\": [file.name for file in uploaded_files], \"Score\": score })\n",
    "    results = results.sort_values(by=\"Score\", ascending=False)\n",
    "    \n",
    "    st.write(results)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "36f4c751-0615-4257-9dd4-36253f1e31e9",
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.12.7"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
