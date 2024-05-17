# RAG-Application-AWS (End-to-End LLMOps Project)

RAG-Application-AWS is an end-to-end LLMOps (Language Model Operations) project for a GenAI RAG (Retrieval and Generation) application powered by Langchain, Bedrock and AWS App Runner service for deployment.

## Getting Started

Follow these steps to set up and deploy the project:

1. **Create GitHub Repository**: Create a new GitHub repository and clone it locally.

2. **Set Up Virtual Environment**: Create a virtual environment and install the required dependencies from `requirements.txt`.

    ```bash
    conda create -p ragproj1 python==3.10 -y
    conda activate ragproj1
    pip install -r requirements.txt
    ```

    Add the virtual environment directory (`ragproj1/`) to `.gitignore` to exclude it from version control.

3. **Create Project Structure**: Set up the main project structure by creating a `SRC/QASystem` directory and adding `__init__.py`, `ingestion.py`, and `retrievalandgeneration.py` files inside. Add code to these files.

4. **Setting Up AWS Configuration**: Create an AWS IAM user with AdministratorAccess policy attached. Configure AWS CLI with the access key and secret key of the IAM user.

5. **Create `app.py`**: Create an `app.py` file and add code to it. This file will serve as the entry point for the application. Run the application using `streamlit run app.py`.

6. **Docker Configuration**: Set up Docker configuration by creating a `Dockerfile` and `.dockerignore`. Add necessary components to `.dockerignore`.

7. **GitHub Actions (CI/CD)**: Create a `.github/workflows` directory and add a `main.yaml` file inside. Configure GitHub Actions for Continuous Integration and Continuous Deployment (CI/CD).

8. **Setting Up AWS ECR Repo**: Create a private AWS Elastic Container Registry (ECR) repository named `ragproj1`. Note down the URI of the repository for later use.

9. **GitHub Secrets and Variables**: Add the following secrets and variables to your GitHub repository:
    - `AWS_ACCESS_KEY_ID`
    - `AWS_SECRET_ACCESS_KEY`
    - `AWS_DEFAULT_REGION`
    - `AWS_ECR_REPO_URI`

10. **Push to GitHub**: Commit and push your work to GitHub to trigger CI/CD actions. This will push the Docker image to the AWS ECR repository.

11. **Deploy to AWS App Runner**: Deploy the ECR image using AWS App Runner service. Provide the URI link of the ECR repository during deployment. Configure the service with necessary settings and deploy the application.

12. **Delete AWS Resources**: After testing, delete the following AWS resources:
    - IAM User (`llmops-proj1`)
    - ECR Repository (`ragproj1`)
    - AWS App Runner Service

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
