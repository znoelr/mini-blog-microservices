# Microservices Blogging App

A microservices-based application that allows users to create posts and add comments to them. The app includes services for post creation, comment management, query storage, content moderation, and event communication.

## Services

### Posts Service

The Posts service allows users to create new posts. It provides endpoints for creating, updating, and deleting posts.

### Comments Service

The Comments service enables users to add comments to a specified post. It manages comment creation, retrieval, and deletion.

### Query Service

The Query service stores posts along with their respective comments, ensuring that posts are always available for users to query. It provides efficient retrieval of posts and associated comments.

### Moderation Service

The Moderation service moderates the text of comments, either approving or rejecting them based on their content. It ensures that comments adhere to community guidelines and maintain a positive user experience.

### Event Bus

The Event Bus service handles event communication between microservices. It facilitates asynchronous communication by allowing services to publish and subscribe to events related to post and comment creation, moderation actions, and more.

## Local Deployment with Skaffold

This project utilizes Skaffold for local deployment, enabling streamlined development and testing of microservices within a Kubernetes environment. Skaffold automates the build, push, and deployment processes, providing a seamless development experience.

To deploy the microservices locally using Skaffold, follow these steps:

1. Install Skaffold: [Skaffold Installation Guide](https://skaffold.dev/docs/install/)
2. Configure Kubernetes: Ensure you have a Kubernetes cluster configured locally (e.g., Minikube, Docker Desktop with Kubernetes enabled).
3. Clone the repository:
  ```bash
  git clone https://github.com/znoelr/mini-blog-microservices.git
  ```
4. Navigate to the project
  ```bash
  cd mini-blog-microservices
  ```
5. Run skaffold
  ```bash
  skaffold dev
  ```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
