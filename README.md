# Phishing Detection and Analysis Tool

## Overview

The Phishing Detection and Analysis Tool is a REST API built with Golang to detect potential phishing attempts in email texts. By leveraging multiple third-party services through a **Facade Pattern**, the tool simplifies integration with various threat intelligence and NLP APIs, providing risk scores based on text content, URLs, and IP addresses found in emails.

The project showcases:
- **Facade Pattern** to simplify and manage multiple external API integrations.
- **NLP and Threat Intelligence** to detect phishing keywords, malicious URLs, and suspicious IPs.
- **Modularity** and **scalability** with well-defined, extensible API interfaces.

---

## Features

- **Text-Based Phishing Detection**: Analyze the content of an email for phishing language and suspicious keywords.
- **Threat Intelligence for URLs and IPs**: Check URLs and IP addresses against known malicious sources.
- **Risk Scoring**: Provides a risk score for each email analyzed, categorizing it as safe or suspicious.

---

## Project Layout

```plaintext
phishing-detection-tool/
│
├── cmd/
│   └── main.go                  # Entry point for the API
│
├── internal/
│   ├── facade/
│   │   ├── facade.go            # Facade interface and implementation
│   │   ├── nlp_service.go       # NLP API integration for text analysis
│   │   ├── url_checker.go       # URL threat intelligence service
│   │   └── ip_checker.go        # IP reputation checker service
│   │
│   ├── handlers/
│   │   └── phishing_handler.go  # API handler for phishing analysis
│   │
│   ├── models/
│   │   └── analysis_result.go   # Structs for results and risk score
│   │
│   ├── services/
│   │   ├── abuseipdb.go         # Integration with AbuseIPDB API
│   │   ├── virustotal.go        # Integration with VirusTotal API
│   │   └── openai_nlp.go        # Integration with OpenAI for NLP
│   │
│   └── utils/
│       └── logger.go            # Logging setup and utilities
│
├── pkg/
│   └── config/
│       └── config.go            # Configuration settings for API keys, etc.
│
├── test/
│   └── phishing_test.go         # Unit tests for phishing detection functionality
│
├── Dockerfile                   # Dockerfile for containerizing the API
├── go.mod                       # Go module dependencies
└── README.md                    # Project overview and documentation

