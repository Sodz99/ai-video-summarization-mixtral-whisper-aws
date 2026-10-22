# AI Video Summarization Project using Mixtral, Whisper, and AWS

The aim of the project is to develop a video summarization and quiz generation tool that leverages Large Language Models and AWS.

## Overview
In today's fast-paced digital landscape, there is a significant demand for efficient educational tools. Traditional learning methods are rapidly evolving, with an increasing prevalence of video-based content. However, the abundance of educational videos available online presents a challenge for learners trying to extract key concepts effectively. This highlights the need for a comprehensive tool that can summarize videos and generate quizzes to help learners understand and retain essential information.

The emergence of large language models (LLMs) like Mixtral and Whisper is transforming the landscape of educational technology platforms. These powerful models use advanced natural language processing techniques to quickly understand and process complex educational content.

## Data
The dataset comprises tutorial videos covering diverse topics such as linear regression and other ML concepts.

_Data is not included in this repository._

## Approach
- Initial Setup: ○ Create AWS EC2 instance with GPU for efficient functioning ○ Create environment and Install necessary dependencies and libraries.
- Model Selection: ○ Select Whisper for audio transcription ○ Choose Mixtral for video summarization and quiz generation
- Transcription Functionality: ○ Extract audio from uploaded videos using FFmpeg ○ Transcribe audio to text using the Whisper model
- Quiz Generation: ○ Use Mixtral to summarize and generate quizzes based on transcribed text ○ Implement different complexity levels for quizzes
- Frontend and API Development: ○ Design a user-friendly interface using HTML and JavaScript

○ Implement file upload functionality for videos

- Feedback Mechanism: ○ Develop a feedback form for user input ○ Store feedback data in a database for analysis

Cost Breakdown

Components:
- LLM models (Whisper for transcription and Mixtral for summarization and quiz generation).
- Hosted on AWS EC2 g5.12xlarge instances with GPU support.
- Requires data storage ( S3) for video files and outputs.

Cost Breakdown as of January 17, 2025 The cost might have been updated, it is recommended to go through the following pricing pages to come up with updated guessestimates. Open AI Pricing https://openai.com/api/pricing/ AWS Pricing https://aws.amazon.com/ec2/capacityblocks/pricing/

Component          Description                      Usage                      Estimated Cost

API Calls        OpenAI Whisper      - Duration: 5-minute video Pricing:       Total: $0.03 (based on        API for             $0.006 per minute                         per video model usage)     transcription

Compute          AWS EC2             1 instance, runs approx. for 15 minutes   Total: ~$3.00 Resources        g5.12xlarge         per video (for a 5-minute video           per video instance with GPU   covering transcription, summarization, support             and quiz generation).- Pricing: $5.672/hour

Storage          S3 storage for        Approx. 200 MB per video- Pricing:     Total: video files and       $0.023 per GB                          $0.0046 per intermediate                                                 video outputs

Network          Data transfer costs   Approx. 200 MB per video- Pricing:     Total: $0.018 Usage            for S3                $0.09 per GB                           per video

Total Costs:

## Tech stack
➔ Language: Python 3.10.4 ➔ Libraries: Flask, FFmpeg, Torch, Transformers, Sqlalchemy ➔ Model: Mixtral, Whisper ➔ Cloud Platform: Amazon Web Services

## How to run
```bash
pip install -r Code Folder/requirements.txt
python Code Folder/run.py
```

## Project structure
```
.gitignore
Code Folder/
  app/
    __init__.py
    data_models/
    database.py
    mixtral_prompts.py
    mixtral_wrapper.py
    routes.py
    templates/
    utils.py
    whisper_wrapper.py
  finetune.py
  readme.md
  requirements.txt
  run.py
README.md
```

## Credits
Based on a ProjectPro guided project.
