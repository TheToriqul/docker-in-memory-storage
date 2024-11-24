# 🚀 Docker In-Memory Storage Implementation

[![GitHub](https://img.shields.io/badge/GitHub-Docker_In_Memory_Storage-blue?style=flat&logo=github)](https://github.com/TheToriqul/docker-in-memory-storage)
[![GitHub stars](https://img.shields.io/github/stars/TheToriqul/docker-in-memory-storage?style=social)](https://github.com/TheToriqul/docker-in-memory-storage/stargazers)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)

## 📋 Overview

This project demonstrates my implementation of secure in-memory storage using Docker containers with tmpfs mounts. Through this journey, I've explored handling sensitive configuration files, such as private keys and API credentials, ensuring they never touch the disk. The project showcases my understanding of container security best practices and memory-based filesystem management.

## 🏗 Technical Architecture

The project implements a microservice-based approach using Docker containers with tmpfs mounts for secure in-memory storage. Here's the high-level architecture:

```mermaid
%%{
    init: {
        'theme': 'base',
        'themeVariables': {
            'primaryColor': '#2B2B2B',
            'primaryTextColor': '#fff',
            'primaryBorderColor': '#7C7C7C',
            'lineColor': '#B0B0B0',
            'secondaryColor': '#383838',
            'tertiaryColor': '#2B2B2B'
        }
    }
}%%

graph TD
    %% Node definitions with descriptive IDs
    CLIENT[Client Request]
    DOCKER[Docker Container]
    PYTHON[Python Microservice]
    TMPFS[tmpfs Mount]
    PROCESS[Data Processing]

    %% Flow definitions with detailed labels
    CLIENT -->|"1. API Call"| DOCKER
    DOCKER -->|"2. Forward Request"| PYTHON
    PYTHON -->|"3. Store Temporarily"| TMPFS
    TMPFS -->|"4. Process In-Memory"| PROCESS
    PROCESS -->|"5. Return Secure Response"| CLIENT

    %% Subgraph for security boundary
    subgraph Secure Environment
        DOCKER
        PYTHON
        TMPFS
        PROCESS
    end

    %% Class definitions optimized for dark mode
    classDef default fill:#2B2B2B,stroke:#B0B0B0,stroke-width:2px,color:#fff
    classDef client fill:#4A148C,stroke:#CE93D8,stroke-width:2px,color:#fff
    classDef container fill:#0D47A1,stroke:#90CAF9,stroke-width:2px,color:#fff
    classDef service fill:#1B5E20,stroke:#A5D6A7,stroke-width:2px,color:#fff
    classDef storage fill:#B71C1C,stroke:#EF9A9A,stroke-width:2px,color:#fff
    classDef process fill:#01579B,stroke:#81D4FA,stroke-width:2px,color:#fff
    classDef notes fill:#424242,stroke:#757575,stroke-width:1px,color:#fff

    %% Apply classes to nodes
    class CLIENT client
    class DOCKER container
    class PYTHON service
    class TMPFS storage
    class PROCESS process

    %% Notes with dark mode optimization
    note1[Secure Data Flow]
    note2[Ephemeral Storage]
    
    class note1,note2 notes
    
    DOCKER -.-> note1
    TMPFS -.-> note2
```

## 💻 Technical Stack

- **Container Platform**: Docker
- **Programming Language**: Python 3.9
- **Base Image**: python:3.9-slim
- **Storage**: tmpfs (memory-based filesystem)
- **File System**: Alpine Linux

## ⭐ Key Features

1. Secure In-Memory Storage
   - tmpfs mount implementation
   - Memory-based file system configuration
   - Secure data handling

2. Docker Configuration
   - Custom Dockerfile setup
   - Container security measures
   - Resource limitation controls

3. Python Microservice
   - Secure file operations
   - Error handling
   - Memory management

4. Security Features
   - No disk persistence
   - Isolated storage space
   - Access control implementation

5. Performance Optimization
   - Memory-only operations
   - Efficient resource usage
   - Quick data access

## 📚 Learning Journey

### Technical Mastery:

1. Docker container configuration and security
2. Memory-based filesystem implementation
3. Microservice architecture design
4. Secure data handling practices
5. Resource management and optimization

### Professional Development:

1. Security-first thinking
2. Documentation best practices
3. Problem-solving with containerization
4. System architecture design
5. Performance optimization techniques

## 🔄 Future Enhancements

<details>
<summary>View Planned Improvements</summary>

1. Implement multiple tmpfs mounts for different security levels
2. Add monitoring and logging capabilities
3. Develop automated testing suite
4. Implement data encryption at rest
5. Add horizontal scaling capabilities
6. Enhance error handling and recovery
</details>

## ⚙️ Installation

<details>
<summary>View Installation Details</summary>

### Prerequisites

- Docker installed on your system
- Python 3.9 or higher
- Basic understanding of containerization

### Setup Steps

1. Clone the repository:
```bash
git clone https://github.com/TheToriqul/docker-in-memory-storage.git
cd docker-in-memory-storage
```

2. Build the Docker image:
```bash
docker build -t my_microservice .
```

3. Run the container:
```bash
docker run --rm -d \
    --mount type=tmpfs,dst=/app/tmp,tmpfs-size=16k,tmpfs-mode=1770 \
    my_microservice
```

</details>

## 📖 Usage Guide

<details>
<summary>View Usage Details</summary>

### Basic Usage

The microservice automatically handles sensitive data in memory. To verify the setup:

1. Check container status:
```bash
docker ps
```

2. Inspect tmpfs mount:
```bash
docker inspect <container_id>
```

### Troubleshooting

- Ensure tmpfs mount is properly configured
- Verify memory allocation is sufficient
- Check container logs for any errors

</details>

## 📫 Contact

- 📧 Email: toriqul.int@gmail.com
- 📱 Phone: +65 8936 7705, +8801765 939006

## 🔗 Project Links

- [GitHub Repository](https://github.com/TheToriqul/docker-in-memory-storage)
- [Documentation](https://github.com/TheToriqul/docker-in-memory-storage/blob/main/README.md)

## 👏 Acknowledgments

- [Poridhi for excellent labs](https://poridhi.io/)
- Docker documentation for tmpfs mount guidance
- Python community for microservice best practices

---

Feel free to explore, modify, and build upon this configuration as part of my learning journey. You're also welcome to learn from it, and I wish you the best of luck!