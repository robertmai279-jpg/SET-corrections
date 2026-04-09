# SET Bias Correction Tool

An interactive web tool that corrects Student Evaluation of Teaching (SET) scores for demographic and structural biases, based on peer-reviewed research.

## About

This tool is based on the article:

> Bashirzadeh, Y., Meunier, L., & Mai, R. (2025). Do Business School Students Value Faculty Diversity? Insights From a Dyadic Analysis of Students' Evaluations of Teaching. *Academy of Management Learning & Education, 25*(1), 10–32. https://doi.org/10.5465/amle.2023.0541

Enter your professor and student profile to receive real-time counterfactual corrections to your SET score, and download a PDF certificate showing the bias-corrected results.

## Features

- 📊 Real-time SET score correction based on regression model coefficients
- 🔄 Counterfactual scenarios for gender, age, grading, employment status, language, and cultural distance
- 📄 Downloadable PDF certificate with your corrected scores and profile summary
- 📱 Responsive design for desktop and mobile

## How to Use

1. Fill in your professor profile (gender, age, employment status, native speaker status)
2. Fill in the student/class profile (gender composition, age, average grade, cultural distance)
3. Enter your current SET score
4. Click **Calculate Corrections** to see all counterfactual adjustments
5. Click **Download PDF Certificate** to save your results

## Hosting on GitHub Pages

1. Fork or clone this repository
2. Go to **Settings → Pages**
3. Under **Source**, select `main` branch and `/ (root)` folder
4. Click **Save**
5. Your tool will be live at `https://<your-username>.github.io/<repo-name>/`

## Local Development

No build step required. Open `index.html` directly in a browser:

```bash
# Option 1: Open directly
open index.html

# Option 2: Serve locally
npx serve .
# or
python3 -m http.server 8080
```

## File Structure

```
set-tool/
├── index.html      # Main tool (self-contained, no dependencies to install)
├── README.md       # This file
└── _config.yml     # GitHub Pages configuration
```

## Dependencies

All dependencies are loaded via CDN (no installation required):

- [Google Fonts](https://fonts.google.com/) — DM Serif Display & DM Sans
- [jsPDF 2.5.1](https://github.com/parallax/jsPDF) — PDF generation

## Statistical Model

The tool implements the regression model from the paper. Coefficients used:

| Variable | Coefficient |
|---|---|
| Euclidean Cultural Distance | −0.0027 |
| Euclidean Cultural Distance² | 0.0002 |
| Professor Gender (Male) | 1.3161 |
| Professor Age | 0.0544 |
| Professor Gender × Age | −0.0442 |
| Professor Age² | −0.0005 |
| Professor Gender × Age² | 0.0003 |
| Student Gender (Male) | 0.2266 |
| Student Gender × Professor Gender | −0.2061 |
| Student Gender × Professor Age | −0.0117 |
| Student Gender × Professor Gender × Age | 0.013 |
| Student Gender × Professor Age² | 0.0001 |
| Student Gender × Professor Gender × Age² | −0.0001 |
| Student Age | 0.0131 |
| Student Grade | 0.0382 |
| Full-time Professor | 0.1006 |
| Native-speaker Professor | 0.0918 |
| Constant | 1.7123 |

## Authors

- [Yashar Bashirzadeh](https://scholar.google.de/citations?user=TUQxeH0AAAAJ&hl=fr&oi=sra)
- [Luc Meunier](https://scholar.google.de/citations?user=z5kg56MAAAAJ&hl=fr&oi=sra)
- [Robert Mai](https://scholar.google.de/citations?user=HJcUHgkAAAAJ&hl=de&oi=sra)

## License

This tool is provided for academic and educational use. Please cite the original paper if you use or reference this tool in your work.
