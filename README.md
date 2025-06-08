# Document Segmentation and NER
This project extracts structured segments from a text document, identifies key metadata such as segment titles, segment dates, and named entities like people, organizations, and locations.

🧠 Approach & Thought Process
Segmentation
We use a regular expression pattern to detect numbered headings like 1. Title, 2. Title, etc. Each heading marks the beginning of a segment.

Entity Recognition
After extracting segment text, we apply a simple NER function to identify:

Persons

Organizations

Locations

Dates

Metadata Extraction
Dates and positions (start/end index) are extracted from each segment for traceability.

Incremental Segment Level Fix
The initial code had segment_level hardcoded to 1. This was corrected to increment with each segment using i + 1.

▶️ How to Run the Solution
1. Install dependencies
Make sure you have Python 3.x and install necessary libraries:

2.Run the notebook
Launch the Jupyter Notebook and execute cells step-by-step:

3.Provide input
Paste or load your raw text into the designated cell to process segments and entities.

📦 Dependencies
re – for regular expression based segmentation

spacy – for Named Entity Recognition

json – to format and visualize the final structured output

📌 Example Output Structure
Each segment is returned as a dictionary with fields like:
{
  "segment_level": 1,
  "segment_title": "Market Overview",
  "segment_text": "...",
  "segment_date": "2022-11-01",
  "start_index": 22,
  "end_index": 413,
  "named_entities": {
    "persons": ["Alice Johnson"],
    "organizations": ["World Bank"],
    "locations": ["New York"],
    "dates": ["2022-11-01"]
  }
}
