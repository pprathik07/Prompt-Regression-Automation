# Prompt Regression Automation

An automated testing system that validates LLM outputs for consistency, accuracy, and quality regressions across multiple prompt iterations.

## Overview

This system automatically tests prompts against LLMs (Gemini, GPT) and detects hallucinations, reasoning drift, and structural inconsistencies in real-time. When issues are detected, it sends automated email alerts for immediate action.

## Features

- **Automated Testing**: Batch execution of prompts with token-level output validation
- **Regression Detection**: Identifies changes in reasoning, tone, structure, and factual accuracy
- **Real-time Alerts**: Email and Telegram notifications for flagged outputs
- **Multi-LLM Support**: Currently supports Gemini API, extensible to other providers
- **Performance Tracking**: Logs regression patterns over time for prompt optimization

## Workflow

1. **Schedule Trigger** → Automated execution at defined intervals
2. **Data Input** → Retrieves test prompts from Google Sheets
3. **LLM Processing** → Executes prompts through Gemini API
4. **Validation** → AI agent performs internal validation with memory tools
5. **Drift Detection** → Compares outputs against expected patterns
6. **Reporting** → Updates tracking sheet and sends alerts if issues detected

## Performance

- Tests 10 prompts with 30+ validation points in under 4 minutes
- Reduces manual review time by 80%+
- Enables iterative prompt refinement at scale

## Tech Stack

- **Automation**: n8n workflow platform
- **LLM API**: Gemini (extensible to OpenAI)
- **Notifications**: Gmail API, Telegram
- **Data Storage**: Google Sheets

## Use Cases

- LLM prompt quality assurance
- Automated regression testing for AI applications
- Content consistency monitoring
- Multi-model performance comparison
