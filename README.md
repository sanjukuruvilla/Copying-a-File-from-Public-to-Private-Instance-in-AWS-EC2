# Copying a File from Public to Private Instance in AWS EC2

This guide provides step-by-step instructions for copying a file from a public EC2 instance to a private EC2 instance in AWS.

## Overview

This repository contains instructions for securely transferring a file from a public EC2 instance to a private EC2 instance using the SCP command. By following these steps, you'll be able to copy files between EC2 instances securely.

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Setup Instructions](#setup-instructions)
3. [Usage](#usage)
4. [Additional Documentation](#additional-documentation)
5. [Contributing](#contributing)
6. [License](#license)

## Prerequisites

Before you begin, ensure you have:

- Access to the AWS Management Console.
- SSH access to both the public and private EC2 instances.
- The `.pem` key file for accessing the EC2 instances.

## Setup Instructions

1. **SSH into Public EC2 Instance**:
   - Connect to the public EC2 instance using SSH.

2. **Copy File from Public to Private Instance**:
   - Use the `scp` command to securely copy the file from the public instance to the private instance.
   - Command:
     ```
     scp -i <pem keyname> <filename> ec2-user@<private instance private ip>:<destination>
     ```
     Example:
     ```
     scp -i key.pem sample.txt ec2-user@10.0.2.131:/home/ec2-user
     ```

3. **SSH into Private EC2 Instance**:
   - Connect to the private EC2 instance using SSH.
   - Command:
     ```
     ssh -i key.pem ec2-user@<private instance private ip>
     ```

4. **Verify File Copy**:
   - Once connected to the private instance, verify that the file has been copied successfully.

## Usage

Follow the provided instructions to securely copy a file from a public EC2 instance to a private EC2 instance. Ensure that you have the necessary permissions and access credentials to perform the file transfer.

## Additional Documentation

For more detailed instructions and additional resources, please refer to the [documentation folder](Documentation/) in this repository. The documentation includes PDF files with detailed guides, best practices, and exercises for practicing.

## Contributing

Contributions to this repository are welcome! If you find issues or have suggestions for improvements, please open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
