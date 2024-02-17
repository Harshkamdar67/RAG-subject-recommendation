
# Student Performance Analysis and Improvement Recommendation System

## Introduction

This system is designed to analyze student performance across various subjects and topics, identify areas where a student may need additional help, and recommend specific study materials to improve their understanding and performance.

## Components

### Data Generation

- **Subjects and Topics**: Defines lists of subjects (`Mathematics`, `Physics`, `Chemistry`) and their respective topics (e.g., `Algebra`, `Geometry`, `Calculus` for Mathematics).
- **Performance Data**: Randomly generates synthetic data for student performance, including `accuracy` (between 40% to 90%) and `average response time` (between 30 to 120 seconds) for each topic in each subject.
- **Content Data**: Lists explanations for each topic in each subject, serving as the study material to be recommended.

### Data Models

- **Performance**: A Pydantic model representing student performance metrics, including accuracy, average response time, subject, and topic.
- **TopicExplanation**: A Pydantic model for educational content, detailing the subject, topic, and a textual explanation of the topic.

### Analysis and Recommendation Logic

1. **Dynamic Thresholds Calculation**: Computes personalized thresholds for determining whether a student's performance in a topic is below expectation, based on the mean and standard deviation of their performance metrics across all topics.

2. **Improvement Area Identification and Recommendation Generation**:
   - Iterates over each student's performance record.
   - If a student's performance (accuracy or response time) falls below the dynamically computed thresholds, the system identifies this as an area needing improvement.
   - Matches the subject and topic with corresponding educational content.
   - Compiles recommendations for each identified area of improvement, including the subject, topic, current performance metrics, and suggested study material.

## Output

The system outputs a list of personalized recommendations for each student, aimed at addressing specific areas of difficulty based on their performance data. Each recommendation includes the subject, topic, the student's current performance metrics in that area, and a suggested study explanation to help improve their understanding and performance.

## Usage

To use this system, provide the synthetic or actual student performance data along with the educational content data. The system will analyze the data, calculate dynamic performance thresholds, identify areas where the student can improve, and generate targeted recommendations for each area.
