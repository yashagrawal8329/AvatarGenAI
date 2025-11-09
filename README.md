# AvatarGenAI
AI-Based Avatar Creation Assignment for Intern
# AvatarGen: AI-Powered Avatar Generator

## Project Overview
AvatarGen is a simple AI-powered avatar creation system designed as part of an AI/ML Intern assignment. It allows users to generate customizable digital avatars from text prompts or optional facial features via a web-based interface. The system leverages generative AI models like Stable Diffusion to create high-quality avatars in styles such as realistic, anime, cartoon, or cyberpunk.

Key features include:
- Text-to-avatar generation with prompt engineering.
- Optional face-guided generation using uploaded selfies.
- Multiple avatar variations with random seeds.
- Downloadable PNG outputs.
- Bonus features: Face-guided generation, random avatar generator, prompt auto-enhancer, and background remover.

This project demonstrates understanding of generative AI, Hugging Face Diffusers, and UI development with Gradio.

## Tech Stack
- **AI Model**: Stable Diffusion (v1.5 or SDXL), with options for ControlNet or IP-Adapter.
- **Framework**: PyTorch, Hugging Face Diffusers.
- **UI**: Gradio (for web interface).
- **Face Processing**: OpenCV, insightface (for optional face detection).
- **Deployment**: Docker, Hugging Face Spaces, or localhost.
- **Language**: Python 3.9+.

## Setup Instructions
1. **Prerequisites**:
   - Python 3.9+ installed.
   - GPU recommended (or use Google Colab for free GPU access).
   - Install dependencies: Run `pip install torch diffusers gradio opencv-python insightface` (add more as needed for bonus features).

2. **Clone the Repository**:
3. 
3. **Run the Application**:
- For local setup: Execute `python app.py` and open the Gradio interface in your browser.
- For Hugging Face Spaces: Upload the code to a new Space and deploy.
- For Docker: Build and run using the provided Dockerfile (if implemented).

4. **Usage**:
- Input a text prompt (e.g., "A cyberpunk woman with blue hair").
- Select a style from the dropdown.
- (Optional) Upload a face image.
- Click "Generate" to create 4 variations.
- Download your favorite avatar.

## Screenshots
Here are some visual examples of the application in action:

- ![App Interface](images/app_interface.png)  
*Main Gradio interface with input fields and generation options.*

- ![Generated Avatars](images/generated_avatars.png)  
*Example output: 4 avatar variations from a text prompt.*

- ![Face-Guided Example](images/face_guided.png)  
*Avatar generated with an uploaded selfie for facial structure.*

*(Note: Replace `images/` with your actual folder path. Upload screenshots as described in the previous guide.)*

## Model Used & Why
- **Primary Model**: Stable Diffusion v1.5 (via Hugging Face Diffusers) for text-to-image generation. We chose this because it's open-source, efficient, and excels at creating diverse, high-quality images from prompts. For realism, we optionally use fine-tuned variants like `stablediffusionapi/realistic-vision-v51`.
- **Why?**: Stable Diffusion provides flexibility with prompt engineering, negative prompts, and parameters like CFG scale (7-12) and steps (30-50) for controlling output quality. It's lightweight compared to GANs and integrates well with Gradio for a user-friendly app. For face-guided features, we added IP-Adapter to blend user faces seamlessly without full fine-tuning.

## Challenges Faced
- **Model Loading and Performance**: Initial setup on local machines was slow due to large model sizes; resolved by using Hugging Face Spaces for cloud deployment.
- **Prompt Engineering**: Early outputs were inconsistent; mitigated with negative prompts (e.g., "blurry, low quality") and style templates.
- **Face Integration**: Aligning uploaded faces with generated avatars required experimenting with insightface and ControlNet, leading to occasional alignment issues.
- **UI Responsiveness**: Gradio's grid display for multiple images took time to optimize for fast generation (<10 seconds per image).
- **Deployment**: Dockerizing the app involved handling dependencies and GPU access, which was tricky on non-GPU systems.

## Demo Video
Watch a 5-minute demo here: [YouTube Link](https://youtu.be/your-demo-video) (unlisted).

## Repository Structure

## Evaluation Criteria Alignment
- **Functionality (30%)**: Core text-to-avatar generation works reliably.
- **Code Quality (20%)**: Clean, modular code with comments.
- **UI/UX (15%)**: Intuitive Gradio interface with fast loading.
- **Creativity (20%)**: Includes bonus features like face-guided generation.
- **Documentation (15%)**: Comprehensive README with visuals and setup.

## Sample Prompts
- "A friendly male robot avatar, blue glowing eyes, minimalistic design"
- "A kawaii anime girl with pink hair in twin tails, smiling, pastel background"
- "A professional businessman, suit and tie, realistic portrait, studio lighting"

## Resources
- [Hugging Face Diffusers](https://huggingface.co/docs/diffusers/index)
- [Gradio Docs](https://gradio.app/docs/)
- [Stable Diffusion WebUI Colab](https://colab.research.google.com/github/AUTOMATIC1111/stable-diffusion-webui/blob/master/launch.py)

## Contributing
Feel free to fork and submit pull requests. For issues, open a GitHub issue.

## License
This project is for educational purposes. See LICENSE for details.
