# AI Resume Builder 🚀

An intelligent resume tailoring tool that uses AI to analyze, optimize, and customize your resume for specific job descriptions. Powered by OpenAI GPT-4 and Google Gemini APIs.

## Features

✨ **Smart Resume Analysis** - Analyzes your resume against job descriptions to identify key matches and gaps

🎯 **Intelligent Resume Tailoring** - Automatically rewrites your resume to align with job requirements

📊 **Gap Analysis** - Identifies missing skills and experiences from job requirements

🔍 **Diff Highlighting** - Shows exactly what changed in your resume with color-coded additions and deletions

✉️ **Cover Letter Generation** - Creates personalized cover letters based on your tailored resume

🤖 **Dual AI Support** - Choose between OpenAI (GPT-4o-mini) or Google Gemini for generation

## How It Works

1. **Input Your Resume** - Provide your existing resume text
2. **Add Job Description** - Paste the target job description
3. **AI Analysis** - The system analyzes gaps between your resume and job requirements
4. **Resume Optimization** - AI rewrites your resume with:
   - Job-relevant keywords
   - Quantified achievements
   - Improved clarity and impact
   - Aligned experience highlights
5. **Cover Letter Creation** - Generates a compelling cover letter matched to the role
6. **Review Changes** - See a diff view highlighting all modifications

## Technologies Used

- **Python** - Core programming language
- **Pydantic** - Data validation and structured outputs
- **OpenAI API** - GPT-4o-mini for text generation and structured parsing
- **Google Gemini API** - Alternative AI model for content generation
- **Jupyter Notebook** - Interactive development environment
- **python-dotenv** - Environment variable management

## Prerequisites

- Python 3.7+
- OpenAI API key
- Google API key (for Gemini)
- Jupyter Notebook or Google Colab

## Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/ai-resume-builder.git
cd ai-resume-builder
```

2. **Install required packages**
```bash
pip install pydantic openai google-generativeai python-dotenv ipython
```

3. **Set up API keys**

Create a `.env` file in the project root:
```env
OPENAI_API_KEY=your_openai_api_key_here
GOOGLE_API_KEY=your_google_api_key_here
```

Or if using Google Colab, add your API keys to Colab secrets.

## Usage

### Quick Start

1. Open the Jupyter notebook:
```bash
jupyter notebook ai-resume-builder.ipynb
```

2. Run the cells sequentially to set up the environment

3. Use the main function to process your resume:

```python
# Run the complete workflow
resume, cover_letter = run_resume_rocket(resume_text, job_description_text)
```

### Individual Functions

**Analyze Resume vs Job Description:**
```python
gap_analysis = analyze_resume_against_job_description(
    job_description_text, 
    resume_text, 
    model="openai"  # or "gemini"
)
```

**Generate Tailored Resume:**
```python
updated_resume = generate_resume(
    job_description_text, 
    resume_text, 
    gap_analysis, 
    model="openai"
)
```

**Generate Cover Letter:**
```python
cover_letter = generate_cover_letter(
    job_description_text, 
    updated_resume.updated_resume, 
    model="openai"
)
```

## Project Structure

```
ai-resume-builder/
├── ai-resume-builder.ipynb    # Main Jupyter notebook with all functionality
├── readme.md                   # Project documentation
└── .env                        # API keys (not tracked in git)
```

## Key Functions

### `openai_generate(prompt, model, temperature, max_tokens, response_format)`
Generates text using OpenAI API with optional structured output parsing.

### `gemini_generate(prompt, temperature, max_output_tokens)`
Generates text using Google Gemini API.

### `analyze_resume_against_job_description(job_description_text, resume_text, model)`
Analyzes resume alignment with job requirements and identifies gaps.

### `generate_resume(job_description_text, resume_text, gap_analysis, model)`
Creates an optimized resume tailored to the job description with diff highlighting.

### `generate_cover_letter(job_description_text, updated_resume, model)`
Generates a personalized cover letter based on the tailored resume.

### `run_resume_rocket(resume_text, job_description_text)`
Executes the complete workflow: analysis → resume generation → cover letter creation.

## Configuration

### Temperature Settings
- **OpenAI**: Default 0.7 (balanced creativity)
- **Gemini**: Default 0.5 (more focused)

### Token Limits
- Default max tokens: 1500
- Adjustable based on resume length

## Example Output

The tool provides:
1. **Gap Analysis** - Structured comparison with:
   - Key job requirements
   - Matching experience
   - Missing qualifications
   - Unique strengths

2. **Updated Resume** - Plain text version optimized for the role

3. **Diff View** - HTML-highlighted version showing:
   - <span style="color:green">Green additions/changes</span>
   - <span style="color:red;text-decoration:line-through">Red deletions</span>

4. **Cover Letter** - Professional 4-paragraph letter addressing the role

## Best Practices

- ✅ Provide detailed resume text with specific achievements
- ✅ Use complete job descriptions with requirements and qualifications
- ✅ Review AI suggestions before finalizing
- ✅ Customize temperature settings for desired creativity level
- ✅ Use OpenAI for structured outputs, Gemini for alternative perspectives

## Limitations

- Requires active API keys with sufficient credits
- AI suggestions should be reviewed for accuracy
- Works best with well-structured input documents
- May require multiple iterations for optimal results

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments

- Built with OpenAI's GPT-4 and Google's Gemini AI models
- Uses Pydantic for robust data validation
- Inspired by the need for efficient job application processes

## Contact

For questions or feedback, please open an issue on GitHub.

---

**Note**: This tool is designed to assist with resume writing, not replace human judgment. Always review and customize AI-generated content before submission.
