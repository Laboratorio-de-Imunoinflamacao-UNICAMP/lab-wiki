# Lab Wiki - Computational Research Guide

Welcome to the **Laboratório de Imunoinflamação - UNICAMP** computational research wiki! This repository serves as a comprehensive guide and knowledge base for documenting computational work, biological data analysis, and bioinformatics workflows used in our laboratory.

## 📚 Table of Contents

- [About](#about)
- [Getting Started](#getting-started)
- [Documentation Structure](#documentation-structure)
- [Best Practices](#best-practices)
- [Tools and Resources](#tools-and-resources)
- [Contributing](#contributing)
- [Support](#support)

## 🔬 About

This wiki is designed to help researchers in our lab:

- **Document** computational workflows and analyses
- **Share** bioinformatics pipelines and scripts
- **Standardize** data analysis procedures
- **Preserve** institutional knowledge
- **Collaborate** more effectively on computational projects

Whether you're working with RNA-seq, flow cytometry data, proteomics, or any other biological data type, this wiki provides a centralized location for documentation and best practices.

## 🚀 Getting Started

### For New Lab Members

1. **Clone this repository** to access all documentation:
   ```bash
   git clone https://github.com/Laboratorio-de-Imunoinflamacao-UNICAMP/lab-wiki.git
   ```

2. **Browse existing documentation** to familiarize yourself with common workflows

3. **Set up your computational environment** following the guidelines in the [Tools and Resources](#tools-and-resources) section

### For Contributing Members

1. **Fork** this repository or create a new branch
2. **Add or update** documentation relevant to your work
3. **Submit a pull request** for review
4. See [Contributing](#contributing) section for detailed guidelines

## 📁 Documentation Structure

We recommend organizing documentation using the following structure:

```
docs/
├── pipelines/           # Bioinformatics pipelines and workflows
│   ├── rna-seq/
│   ├── proteomics/
│   └── flow-cytometry/
├── protocols/           # Computational protocols and SOPs
├── scripts/             # Reusable analysis scripts
│   ├── r/
│   ├── python/
│   └── bash/
├── tutorials/           # Step-by-step tutorials
├── data-management/     # Data organization and storage guidelines
└── troubleshooting/     # Common issues and solutions
```

### What to Document

When documenting your computational work, include:

- **Purpose**: What question are you trying to answer?
- **Input data**: What type of data, format, and source
- **Methods**: Step-by-step procedures, tools, and parameters used
- **Output**: What results are generated and how to interpret them
- **Dependencies**: Software versions, packages, and requirements
- **Example code**: Reproducible code snippets or full scripts
- **References**: Papers, tools, or resources used

## ✅ Best Practices

### Code Documentation

- Use clear, descriptive variable and function names
- Comment your code to explain complex logic
- Include a header with script purpose, author, and date
- Document all parameters and expected inputs/outputs

### Data Analysis

- **Reproducibility**: Use version control (git) for all scripts
- **Environment management**: Use conda, Docker, or similar tools to manage dependencies
- **File organization**: Follow a consistent directory structure for projects
- **Backup**: Regularly backup data and code to appropriate storage
- **Version tracking**: Document software versions and analysis dates

### Documentation

- Write clear, concise documentation in Markdown format
- Include visual aids (plots, flowcharts) when helpful
- Keep documentation up-to-date as methods evolve
- Use descriptive commit messages when updating documentation

## 🛠️ Tools and Resources

### Recommended Software

#### Programming Languages
- **R**: Statistical analysis, visualization (RStudio, Bioconductor)
- **Python**: Data processing, machine learning (Jupyter, pandas, scikit-learn)
- **Bash**: Automation and pipeline development

#### Bioinformatics Tools
- **Alignment**: STAR, BWA, Bowtie2
- **Quality Control**: FastQC, MultiQC
- **Differential Expression**: DESeq2, edgeR, limma
- **Variant Calling**: GATK, bcftools
- **Visualization**: IGV, UCSC Genome Browser

#### Environment Management
- **Conda/Mamba**: Package and environment management
- **Docker/Singularity**: Containerization for reproducibility

#### Version Control
- **Git/GitHub**: Code versioning and collaboration

### Learning Resources

- [Bioconductor](https://www.bioconductor.org/): R packages for bioinformatics
- [Galaxy Project](https://galaxyproject.org/): Web-based platform for data analysis
- [NCBI Resources](https://www.ncbi.nlm.nih.gov/): Databases and tools
- [Software Carpentry](https://software-carpentry.org/): Programming and data science tutorials

## 🤝 Contributing

We encourage all lab members to contribute to this wiki! Here's how:

### Adding New Content

1. **Create a new branch** for your contribution:
   ```bash
   git checkout -b add-rnaseq-pipeline
   ```

2. **Add your documentation** in the appropriate directory

3. **Commit your changes** with a descriptive message:
   ```bash
   git add .
   git commit -m "Add RNA-seq pipeline documentation"
   ```

4. **Push to GitHub** and create a pull request:
   ```bash
   git push origin add-rnaseq-pipeline
   ```

### Updating Existing Content

- If you find errors or outdated information, please update it
- Document significant changes in your commit message
- Consider discussing major changes with the team first

### Contribution Guidelines

- Use clear, accessible language
- Include practical examples when possible
- Test your code before documenting it
- Respect data privacy and security guidelines
- Follow the documentation structure outlined above

## 📞 Support

If you have questions or need help:

- **Lab meetings**: Discuss computational approaches during regular meetings
- **GitHub Issues**: Open an issue in this repository for documentation questions
- **Email**: Contact the bioinformatics lead in the lab

## 📄 License

This documentation is available under the MIT License. See [LICENSE](LICENSE) for details.

---

**Last Updated**: January 2026  
**Maintained by**: Laboratório de Imunoinflamação - UNICAMP