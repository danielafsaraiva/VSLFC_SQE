# Repository for "Paper"

This repository contains the supplementary data for the research article submitted to **To be Added**. It includes coded light fields, original source views, subjective results, and encoding configurations.

---

## 1. Directory Structure

- `/coded_LFs`: Contains sub-folders for each method (`Pleno3x3`, `Pleno5x5`, `VVC3x3`, `VVC5x5`).
- `/configs`: CSV files (`jpeg_pleno_cfg.csv`, `vvc_cfg.csv`) with encoding parameters.
- `/originals_LFs`: The original source views (inner 5x5 grid).
- `/thurstone_results`: CSV files containing the Thurstone subjective data.

---

## 2. File Nomenclature (Coded PNGs)

The PNG files in the `/coded` directory follow this naming convention:  
**`[LF_Name]_[CodingMethod]_[Row]_[Col]_[Lambda_or_QP].png`**

**Example:** `Bicycle_Pleno3x3_002_004_2840.png`
* **LF_Name**: Source light field (e.g., *Bicycle*).
* **CodingMethod**: The codec and method used (e.g., *Pleno3x3*).
* **Row/Col**: Vertical and horizontal index of the view within the 5x5 grid.
* **Lambda/QP**: The specific control parameter value used for that encoding.
    * For **JPEG Pleno**, this is the **Lambda ($\lambda$)** value.
    * For **VVC**, this is the **Quantization Parameter (QP)**.

---

## 3. Configuration Parameters (`/configs`)

The configuration tables provide the exact settings used to obtain the coded light fields. Note the specific control parameters used for each standard:

* **For VVC**: The **QP** (Quantization Parameter) is used for the **VTM reference software** under the Random Access configuration.
* **For JPEG Pleno**: The **Lambda ($\lambda$)** variable is used to control the **Rate-Distortion tradeoff in JPEG Pleno 4D-TM**.

### Column Descriptions
| Column | Description |
| :--- | :--- |
| **Scene** | The name of the source light field content. |
| **Coding Method** | The specific codec configuration (Pleno 3x3/5x5 or VVC 3x3/5x5). |
| **Lambda / QP** | The primary rate control parameter ($\lambda$ for JPEG Pleno; QP for VVC). |
| **Target Bitrate** | The intended bitrate in bits per pixel (bpp). |
| **BPP** | The actual resulting bitrate (bits per pixel) of the encoded light field. |
| **Rate** | The nomenclature identifier ($R_1, R_2, R_3, R_4$) used in subjective results. |

### Rate Mapping
| Identifier | Target Bitrate (bpp) | Description |
| :--- | :--- | :--- |
| **R1** | 0.118 | Lowest bitrate point |
| **R2** | 0.236 | Low-medium bitrate point |
| **R3** | 0.472 | Medium-high bitrate point |
| **R4** | 1.003 | Highest bitrate point |

---

## 4. Thurstone Subjective Results (`/thurstone results`)

Subjective quality scores are provided for **Cross-Codec** and **Cross-Method** comparisons.

### View Type Selection
Three views were selected for each light field based on the lowest MS-SSIM at the highest bitrate ($R_4$) when processed via the VTM-synthesized pipeline.

| Scene | View Type | View Index (Row_Col) | Description |
| :--- | :--- | :--- | :--- |
| **Bicycle** | 0 | 004_002 | Original compressed view |
| **Bicycle** | 1 | 004_001 | 1st-generation synthesized |
| **Bicycle** | 2 | 003_001 | 2nd-generation synthesized |

*(Note: Add other scenes to this table as applicable)*

### CSV Data Description
The files utilize the **Thurstone Case V model** to estimate a quality scale where higher values indicate better perceived quality.

| Column | Description |
| :--- | :--- |
| **scene** | The light field name and view type (e.g., `Bicycle_0`). |
| **condition** | The coding configuration and bitrate level (e.g., `Pleno3x3_R1`). |
| **jod** | Just Objectionable Difference; the estimated quality score (normalized to [0,1]). |
| **jod_low / jod_high** | Lower and upper bounds for the JOD score. |
| **CIlow / CIhigh** | Lower and upper bounds of the confidence intervals. |

---

## 5. Contact & Feedback
*Note to Co-authors: Please review the nomenclature and data structure. Suggest any alterations via the Issues tab or by editing this file directly.*
