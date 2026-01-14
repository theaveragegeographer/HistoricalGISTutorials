# Contributing to Historical GIS Tutorials

Thank you for your interest in contributing to this educational resource! This guide will help you contribute effectively.

## Ways to Contribute

### 1. Report Issues
- Typos or errors in tutorials
- Broken links
- Unclear instructions
- Technical inaccuracies
- Missing prerequisites

### 2. Suggest Improvements
- Additional topics to cover
- Better examples or exercises
- Alternative approaches
- Updated software instructions
- New resources or datasets

### 3. Add Content
- New tutorial chapters
- Case studies
- Example projects
- Sample datasets
- Additional exercises

### 4. Share Your Experience
- How you used these tutorials
- Projects you completed
- Challenges you faced
- Solutions you found

## How to Contribute

### Reporting Issues

1. Check if the issue already exists
2. Create a new issue with:
   - Clear, descriptive title
   - Detailed description
   - Which tutorial/file is affected
   - Expected vs actual behavior
   - Screenshots if applicable

### Suggesting Enhancements

1. Open an issue with the "enhancement" label
2. Describe the suggestion clearly
3. Explain why it would be valuable
4. Provide examples if possible

### Contributing Content

#### Small Changes (typos, minor edits)

1. Fork the repository
2. Create a branch: `git checkout -b fix-typo-tutorial-01`
3. Make your changes
4. Commit: `git commit -m "Fix typo in Getting Started tutorial"`
5. Push: `git push origin fix-typo-tutorial-01`
6. Open a Pull Request

#### Large Changes (new tutorials, major additions)

1. Open an issue first to discuss the proposed addition
2. Get feedback from maintainers
3. Fork the repository
4. Create a branch: `git checkout -b add-gis-database-tutorial`
5. Add your content following the style guide below
6. Test your instructions (make sure they work!)
7. Commit with clear messages
8. Push and open a Pull Request

## Style Guide

### Markdown Files

- Use clear, concise language
- Write for beginners (avoid jargon or explain it)
- Use active voice
- Break content into sections with headers
- Include examples

### Tutorial Structure

Each tutorial should include:

1. **Introduction**: What the tutorial covers
2. **Learning Objectives**: What students will learn
3. **Prerequisites**: What they need to know first
4. **Step-by-step instructions**: Clear, numbered steps
5. **Examples**: Real-world applications
6. **Exercises**: Practice activities
7. **Troubleshooting**: Common problems and solutions
8. **Resources**: Additional reading/data
9. **Next Steps**: Where to go from here

### Markdown Formatting

```markdown
# Main Title (H1 - only once per document)

## Major Section (H2)

### Subsection (H3)

**Bold** for emphasis or UI elements
*Italic* for terms or subtle emphasis
`Code` for commands, file names, technical terms

- Bullet lists for items
1. Numbered lists for sequential steps

[Link text](URL)

> Blockquote for important notes
```

### Code Blocks

Use fenced code blocks with language specification:

```python
# Python example
print("Hello, Historical GIS!")
```

```sql
-- SQL example
SELECT * FROM cities WHERE founded < 0;
```

### Images

If adding images:
1. Place in an `images/` subdirectory
2. Use descriptive filenames: `qgis-buffer-dialog.png`
3. Include alt text: `![QGIS Buffer Tool Dialog](images/qgis-buffer-dialog.png)`
4. Keep file sizes reasonable (< 500KB)

### Historical Content

When writing about history:
- Be accurate and cite sources
- Present multiple perspectives when appropriate
- Acknowledge uncertainty
- Avoid presentism
- Be sensitive to cultural contexts
- Use BCE/CE date notation

### Technical Content

When writing technical instructions:
- Test everything yourself first
- Include software version information if relevant
- Provide screenshots for complex steps
- Explain why, not just how
- Anticipate common errors
- Include troubleshooting tips

## Sample Datasets

When contributing sample data:

1. **Document the source**: Where did this data come from?
2. **Check the license**: Can we legally share it?
3. **Clean the data**: Remove errors, standardize format
4. **Keep it manageable**: Not too large (< 1MB preferred)
5. **Include metadata**: What do the fields mean?
6. **Provide attribution**: Credit original creators
7. **Consider privacy**: No sensitive personal information

### Data File Formats

Prefer:
- CSV for tabular data (simple, universal)
- GeoJSON for vector geographic data (readable, modern)
- Markdown for documentation

Avoid proprietary formats unless necessary.

## Licensing

By contributing, you agree that your contributions will be licensed under the same license as the project (for academic and educational use).

## Code of Conduct

### Our Standards

- Be respectful and inclusive
- Welcome newcomers
- Provide constructive feedback
- Focus on what's best for the community
- Show empathy

### Unacceptable Behavior

- Harassment or discriminatory language
- Personal attacks
- Trolling or insulting comments
- Publishing others' private information
- Unprofessional conduct

## Review Process

1. **Submission**: You submit a pull request
2. **Initial Review**: Maintainer checks basic requirements
3. **Technical Review**: Content accuracy is verified
4. **Testing**: Instructions are tested if applicable
5. **Feedback**: You may be asked to make changes
6. **Approval**: Once approved, content is merged
7. **Credit**: You're added to contributors list

## Getting Help

- Open an issue for questions
- Tag with "question" label
- Be specific about what you need help with
- Include what you've already tried

## Recognition

Contributors are acknowledged in:
- Repository contributors list
- Tutorial acknowledgments (for significant contributions)
- Project documentation

## Questions?

If you're unsure about anything, please ask! Open an issue with the "question" label.

## Thank You!

Your contributions help make historical GIS accessible to more researchers and students. Every contribution, no matter how small, is valuable!

---

## Quick Checklist for Contributors

Before submitting:

- [ ] Content is accurate and tested
- [ ] Spelling and grammar checked
- [ ] Links work
- [ ] Images load properly
- [ ] Code examples run correctly
- [ ] Follows style guide
- [ ] Appropriate citations included
- [ ] Clear commit messages
- [ ] Pull request describes changes

Thank you for contributing to Historical GIS Tutorials!
