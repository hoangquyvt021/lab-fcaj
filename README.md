# Hybrid DNS with Route 53 Resolver Workshop

[![AWS](https://img.shields.io/badge/AWS-Route%2053-orange)](https://aws.amazon.com/route53/)
[![Hugo](https://img.shields.io/badge/Hugo-Static%20Site-blue)](https://gohugo.io/)
[![License](https://img.shields.io/badge/License-MIT--0-green)](LICENSE)

A comprehensive hands-on workshop for implementing hybrid DNS architecture using AWS Route 53 Resolver, enabling seamless integration between on-premises DNS systems and AWS cloud infrastructure.

## 🎯 Overview

This workshop guides you through building a hybrid DNS system that bridges your existing on-premises DNS infrastructure with Amazon Route 53. Learn to configure Route 53 Resolver endpoints, forwarding rules, and establish bidirectional DNS resolution between AWS and on-premises environments.

### What You'll Learn

- Configure Route 53 Resolver inbound and outbound endpoints
- Set up DNS forwarding rules for hybrid connectivity
- Integrate Microsoft Active Directory with AWS DNS services
- Implement secure DNS resolution across hybrid environments
- Best practices for DNS architecture in AWS

## 🏗️ Architecture

The workshop implements a hybrid DNS architecture featuring:

- **AWS Route 53 Resolver** for cloud DNS services
- **On-premises DNS servers** (Microsoft AD)
- **Inbound/Outbound endpoints** for bidirectional resolution
- **VPC integration** with proper security groups
- **Remote Desktop Gateway** for secure access

## 📚 Workshop Content

| Section | Topic | Description |
|---------|-------|-------------|
| 1 | [Introduction](content/1-Introduce/) | Overview of hybrid DNS concepts and Route 53 Resolver |
| 2 | [Prerequisites](content/2-Prerequiste/) | Environment setup, key pairs, and CloudFormation deployment |
| 3 | [Connect to RDGW](content/3-Connecttordgw/) | Establishing secure connection to Remote Desktop Gateway |
| 4 | [Microsoft AD Setup](content/4-SetupAD/) | Deploying and configuring Active Directory services |
| 5 | [Hybrid DNS Configuration](content/5-SetupHyridDNS/) | Route 53 Resolver endpoints and forwarding rules |
| 6 | [Cleanup](content/6-Cleanup/) | Resource cleanup and cost optimization |

## 🚀 Quick Start

### Prerequisites

- AWS Account with appropriate permissions
- Hugo static site generator (v0.25+)
- Git for version control
- Basic understanding of DNS and AWS networking

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/AWS-First-Cloud-Journey/000010-HybridDNS-Route53.git
   cd 000010-HybridDNS-Route53
   ```

2. **Install Hugo** (if not already installed)
   ```bash
   # macOS
   brew install hugo
   
   # Ubuntu/Debian
   sudo apt-get install hugo
   
   # Windows
   choco install hugo
   ```

3. **Start development server**
   ```bash
   hugo server -D
   ```

4. **Access the site**
   Open http://localhost:1313 in your browser

### Building for Production

```bash
# Generate static files
hugo

# Files will be generated in the ./public directory
```

## 🌐 Multi-language Support

This workshop is available in multiple languages:

- **English** (`/en/`) - Primary language
- **Vietnamese** (`/vi/`) - Tiếng Việt

Language switching is available through the site navigation.

## 📁 Project Structure

```
├── config.toml              # Hugo configuration
├── content/                 # Workshop content (Markdown)
│   ├── 1-Introduce/        # Introduction section
│   ├── 2-Prerequiste/      # Prerequisites and setup
│   ├── 3-Connecttordgw/    # RDGW connection guide
│   ├── 4-SetupAD/          # Active Directory setup
│   ├── 5-SetupHyridDNS/   # Hybrid DNS configuration
│   └── 6-Cleanup/          # Resource cleanup
├── static/                  # Static assets (images, CSS)
├── layouts/                 # Custom Hugo layouts
├── themes/                  # Hugo theme (hugo-theme-learn)
├── public/                  # Generated static site
└── Architecture.drawio      # Architecture diagram source
```

## 🎨 Theme & Customization

- **Theme**: [Hugo Learn Theme](https://github.com/matcornic/hugo-theme-learn)
- **Variant**: Workshop theme with AWS branding
- **Features**: 
  - Search functionality
  - Responsive design
  - Syntax highlighting
  - Mermaid diagram support
  - Multi-language navigation

### Custom Styling

Custom CSS and theme modifications are located in:
- `static/css/theme-workshop.css`
- `layouts/partials/custom-footer.html`
- `layouts/partials/logo.html`

## 🔧 Configuration

Key configuration options in `config.toml`:

```toml
theme = "hugo-theme-learn"
[params]
  themeVariant = "workshop"
  author = "journeyoftheaverageguy@gmail.com"
  showVisitedLinks = true
  disableBreadcrumb = false
```

## 🚀 Deployment Options

### Static Hosting
Deploy the `public/` folder to any static hosting service:
- **AWS S3 + CloudFront**
- **GitHub Pages**
- **Netlify**
- **Vercel**

### AWS S3 Deployment Example
```bash
# Build the site
hugo

# Sync to S3 bucket
aws s3 sync public/ s3://your-bucket-name --delete
```

## 🤝 Contributing

We welcome contributions to improve this workshop:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Create a Pull Request

### Content Guidelines

- Follow the existing content structure
- Include both English and Vietnamese translations
- Add relevant screenshots and diagrams
- Test all AWS procedures before submitting
- Ensure proper markdown formatting

## 📋 Workshop Requirements

### AWS Services Used
- Amazon Route 53 & Route 53 Resolver
- Amazon VPC
- Amazon EC2
- AWS Directory Service
- AWS CloudFormation

### Estimated Costs
- Workshop duration: 2-3 hours
- Estimated cost: $10-20 USD (varies by region)
- Remember to clean up resources after completion

## 🔗 Related Resources

- [AWS Route 53 Documentation](https://docs.aws.amazon.com/route53/)
- [Route 53 Resolver Documentation](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resolver.html)
- [AWS First Cloud Journey](https://cloudjourney.awsstudygroup.com)
- [AWS Study Group Facebook](https://www.facebook.com/groups/awsstudygroupfcj)

## 📄 License

This project is licensed under the MIT-0 License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- **Issues**: Report bugs or request features via [GitHub Issues](https://github.com/AWS-First-Cloud-Journey/000010-HybridDNS-Route53/issues)
- **Community**: Join the [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj)
- **Documentation**: Visit [AWS First Cloud Journey](https://cloudjourney.awsstudygroup.com)

---

**Part of the AWS First Cloud Journey Series**  
Learn AWS through hands-on workshops and real-world scenarios.
