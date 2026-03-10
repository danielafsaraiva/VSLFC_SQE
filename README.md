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
Here is the complete, final README.md in Markdown format, incorporating the precise technical definitions, rate mapping, and the specific view indices for each light field.
Markdown

# TCSVT_rep: Supplementary Material for Light Field Coding Evaluation

This repository contains the supplementary data for the research article submitted to **IEEE TCSVT**. It includes coded light fields, original source views, Thurstone subjective scaling results, and encoding configurations.

---

## 1. Directory Structure

- `/coded`: Sub-folders for each method (`Pleno3x3`, `Pleno5x5`, `VVC3x3`, `VVC5x5`).
- `/configs`: CSV files (`jpeg_pleno_cfg.csv`, `vvc_cfg.csv`) with encoding parameters.
- `/originals_5x5`: The original source views (inner 5x5 grid).
- `/thurstone results`: CSV files containing the Thurstone subjective scaling data.
- **Coded Light Fields**: Due to file size constraints, the coded PNGs are provided as ZIP archives in the [Releases section](../../releases).

---

## 2. File Nomenclature (Coded PNGs)

The PNG files in the `/coded` directory follow this naming convention:  
**`[LF_Name]_[CodingMethod]_[Row]_[Col]_[Lambda_or_QP].png`**

* **LF_Name**: Source light field (e.g., *Bicycle*).
* **CodingMethod**: The codec and method used (e.g., *Pleno3x3*).
* **Row/Col**: Vertical and horizontal index of the view within the 5x5 grid.
* **Lambda/QP**: The specific control parameter value used for that encoding.
    * For **JPEG Pleno**, this is the **Lambda ($\lambda$)** value.
    * For **VVC**, this is the **Quantization Parameter (QP)**.

---

## 3. Configuration Parameters (`/configs`)

The configuration tables provide the exact settings used to obtain the coded light fields, ensuring experimental reproducibility. 

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

Subjective quality scores are provided for **Cross-Codec** (Pleno vs. VVC) and **Cross-Method** ($5\times5$ vs. $3\times3$) comparisons.

### View Type Selection
For each light field, three specific views were selected from the inner $5 \times 5$ grid to represent different synthesis generations:
* **View Type 0**: Original compressed views.
* **View Type 1**: First-generation synthesized views.
* **View Type 2**: Second-generation synthesized views.

The specific views chosen for each light field were determined by identifying the view with the lowest **MS-SSIM** at the highest bitrate ($R_4$) when processed via the VVC $3\times3$ sparsely sampled and synthesized pipeline.

### Selected View Indices
| Scene | View Type | View Index (Row_Col) |
| :--- | :---: | :--- |
| **Bicycle** | 0 | 004_002 |
| **Bicycle** | 1 | 004_001 |
| **Bicycle** | 2 | 003_001 |
| **Bikes** | 0 | 002_000 |
| **Bikes** | 1 | 000_001 |
| **Bikes** | 2 | 001_001 |
| **Fountain** | 0 | 002_000 |
| **Fountain** | 1 | 004_003 |
| **Fountain** | 2 | 003_003 |
| **Sideboard** | 0 | 000_002 |
| **Sideboard** | 1 | 003_004 |
| **Sideboard** | 2 | 003_003 |

### CSV Data Description
The subjective test used a **pairwise comparison** method in which subjects identified which stimulus showed the most flicker. Consequently, the results use the **Thurstone Case V model** to estimate a quality scale in which **higher values indicate greater perceived flicker (lower quality)**.

