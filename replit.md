# Social Media Sentiment Analysis Application

## Overview

This repository contains a Streamlit-based web application for analyzing sentiment from social media content. The application allows users to upload data from various social media platforms (Instagram, Facebook, and X/Twitter) or analyze individual posts. It provides sentiment classification (positive, neutral, negative) and various visualizations to help understand sentiment patterns.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

The application follows a modular architecture with clear separation of concerns:

1. **Web Interface (Streamlit)**: Handles user interactions and displays results
2. **Data Processing**: Manages loading and preprocessing of social media data
3. **Sentiment Analysis**: Performs sentiment analysis on text data
4. **Data Visualization**: Creates interactive charts and visualizations

The application is designed to run as a standalone web service, making it accessible through a browser and deployable to cloud environments.

## Key Components

### 1. Web Interface (`app.py`)

Acts as the main entry point and orchestrates the application flow. It:
- Provides a streamlined interface for users to upload data or enter text
- Handles input validation and user feedback
- Organizes the layout and presents visualization components
- Manages session state for storing data between interactions

### 2. Data Processor (`data_processor.py`)

Responsible for:
- Loading data from CSV or JSON files
- Validating and preprocessing data structure
- Identifying text content columns
- Converting data into a standardized format for analysis

The processor is designed to handle various social media data formats and automatically detect the relevant text columns.

### 3. Sentiment Analyzer (`sentiment_analyzer.py`)

Implements sentiment analysis using a hybrid approach:
- NLTK's VADER (Valence Aware Dictionary and sEntiment Reasoner)
- TextBlob for additional polarity analysis
- Combines both methods for more accurate sentiment classification

The analyzer categorizes text as positive, neutral, or negative based on computed sentiment scores.

### 4. Data Visualizer (`data_visualizer.py`)

Creates interactive visualizations using Plotly and WordCloud:
- Sentiment distribution charts
- Platform-based sentiment analysis
- Word clouds of most frequent terms by sentiment category
- Time-series sentiment analysis

### 5. Sample Data

The repository includes sample datasets for testing:
- `facebook_sample.csv`
- `instagram_sample.csv`
- `twitter_sample.csv`

These files contain structured social media posts with dates, content, engagement metrics, and platform information.

## Data Flow

1. **Input**: User uploads social media data file or enters individual text
2. **Processing**: Data is loaded, validated, and preprocessed
3. **Analysis**: Sentiment analysis is performed on the text content
4. **Visualization**: Results are presented in charts and graphs
5. **Filtering**: Users can filter and drill down into specific segments of data

## External Dependencies

The application relies on the following key Python libraries:

1. **Streamlit**: Web application framework
2. **NLTK**: Natural language processing and sentiment analysis
3. **TextBlob**: Simplified text processing and sentiment scoring
4. **Pandas**: Data manipulation and analysis
5. **Plotly**: Interactive data visualization
6. **WordCloud**: Generating word clouds from text data

All dependencies are specified in `pyproject.toml` and should be installed automatically.

## Deployment Strategy

The application is configured for deployment with the following characteristics:

1. **Server Configuration**:
   - Headless mode enabled
   - Running on port 5000
   - Accessible from any IP (0.0.0.0)

2. **Replit Deployment**:
   - Uses Python 3.11 runtime
   - Configured for autoscale deployment
   - Run command: `streamlit run app.py --server.port 5000`

3. **Workflow Configuration**:
   - Run button configured to execute "Project" workflow
   - Project workflow runs the Streamlit server in parallel mode

The application is ready for cloud deployment and can be accessed via web browser once deployed.

## Development Notes

- The sentiment analysis implementation uses a hybrid approach for better accuracy
- Additional social media platforms can be supported by extending the data processor
- The visualization components are modular and can be extended with new chart types
- Sample data is provided for testing, but the application is designed to work with real social media export data

## Future Enhancements

Potential areas for improvement:
- More advanced NLP techniques for sentiment analysis
- Support for additional languages
- Deeper analytics on engagement metrics
- Export functionality for processed data
- User authentication for private data analysis
