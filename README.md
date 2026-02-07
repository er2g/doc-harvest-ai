# Doc Harvest AI

End-to-end Turkish document processing pipeline: Google Drive ingestion, OCR extraction, and Gemini-based analysis.

## Pipeline

1. Download folder content from Google Drive (service account)
2. Convert documents/images to text with EasyOCR (+ GPU when available)
3. Analyze OCR text in chunks with Vertex AI Gemini
4. Produce structured outputs and summary reports

## Features

- Drive folder crawling and export handling
- OCR for PDF, PPTX, and image files
- Web UI for run control and live logs
- CLI scripts for each pipeline stage

## Requirements

- Python 3.9+
- `pip install -r requirements.txt`
- Google Cloud credentials for Drive + Vertex AI
- Optional CUDA-enabled PyTorch setup for GPU OCR

## CLI Examples

Download from Drive:

```bash
python drive_fetch.py <FOLDER_ID> <OUTPUT_DIR> --service-account /path/to/sa.json
```

Run OCR:

```bash
python gpu_turkish_ocr.py <SOURCE_DIR>
```

## Project Layout

- `drive_fetch.py`: Drive downloader
- `gpu_turkish_ocr.py`: OCR stage
- `analyze_ocr_outputs.py`: Gemini analysis stage
- `web_app/`: browser-based control panel
