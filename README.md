# TCSVT_rep: Supplementary Material for Light Field Coding Evaluation

This repository contains the supplementary data for the research article submitted to **IEEE TCSVT**. it includes coded light fields, original source views, subjective scaling results, and encoding configurations.

---

## 1. Directory Structure

- `/coded`: Contains sub-folders for each method (`Pleno3x3`, `Pleno5x5`, `VVC3x3`, `VVC5x5`).
- `/configs`: CSV files (`jpeg_pleno_cfg.csv`, `vvc_cfg.csv`) with encoding parameters.
- `/originals_5x5`: The original source views (inner 5x5 grid).
- `/thurstone results`: CSV files containing the Thurstone subjective scaling data.

---

## 2. File Nomenclature (Coded PNGs)
The files in the `/coded` directory follow this format:  
`[LF_Name]_[Method]_[Row]_[Col]_[Bitrate_Identifier].png`

**Example:** `Bicycle_Pleno3x3_002_004_2840.png`
* **LF_Name**: Source light field.
* **Method**: Codec/Method (e.g., Pleno3x3).
* **Row/Col**: Vertical and horizontal view index.
* **Bitrate_Identifier**: Identifier linked to the bitstream size in the config files.

---

## 3. Configuration Parameters
The CSVs in `/configs` describe the experimental points:
* **Target Bitrate**: Intended bitrate (bpp).
* **Lambda**: RD-tradeoff parameter for JPEG Pleno.
* **QP**: Quantization Parameter for VVC (VTM).
* **Bitstream (bytes)**: Total file size.
* **Bitrate**: Final resulting bitrate in bpp.

---

## 4. Subjective Testing Details
Subjective scores are provided in `/thurstone results`. For these tests, specific representative views were selected from the 5x5 grid:
* **Central**: (002, 002)
* **Horizontal**: (002, 004)
* **Vertical**: (004, 002)
* **Diagonal**: (004, 004)

---

## 5. Contact & Feedback
*Note to Co-authors: Please review the nomenclature and data structure. Suggest any alterations via the Issues tab or by editing this file directly.*
