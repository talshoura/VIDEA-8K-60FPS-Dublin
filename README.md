<a id="idtext"></a> 
# VIDEA-Dublin Dataset
Please feel free to [**view and download the dataset here**](https://drive.google.com/drive/folders/1vphE2Eg-s-efnLFPShE_WomJXjZjkmlS?usp=sharing) \
For comments, feedback, or question please [Contact Us](mailto:Tariq.AlShoura@ucalgary.ca?subject=Inquiry%20about%20the%20SEPE%208K%20Dataset) at: [Tariq.AlShoura@ucalgary.ca](mailto:Tariq.AlShoura@ucalgary.ca?subject=Inquiry%20about%20the%20SEPE%208K%20Dataset)



<!-- **Please cite the following paper if using the dataset:**
> Tariq Al Shoura, Ali Mollaahmadi Dehaghi, Reza Razavi, and Mohammad Moshirpour. 2025. VIDEA-8K-60FPS Dataset: 8K 60FPS Video Sequences for Analysis and Development. In Proceedings of the 33rd ACM International Conference on Multimedia (MM ’25), October 27–31, 2025, Dublin, Ireland.
ACM, New York, NY, USA, 7 pages. https://doi.org/10.1145/3746027.3758278 -->

<br><br>

### Please checkout the [**main dataset page here**](https://github.com/talshoura/VIDEA-8K-60FPS-Dataset) :
> **GitHub:** https://github.com/talshoura/VIDEA-8K-60FPS-Dataset <br>
> **Paper:** https://doi.org/10.1145/3746027.3758278

<br>

## Table of Contents
- [Dataset Overview](#dataset-overview)
   * [Videos Samples Preview](#videos-samples-preview)
- [Dataset Gathering and Generation](#dataset-gathering-and-generation)
   * [Encoding Quality](#encoding-quality)
- [Dataset Characteristics ](#dataset-characteristics)
   * [Spatial and Temporal Perceptual Information Distribution of the Dataset's Videos.](#spatial-and-temporal-perceptual-information-distribution-of-the-datasets-videos)
   * [Average Motion Distribution of the Dataset's Videos.](#average-motion-distribution-of-the-datasets-videos)
   * [Contrast and Colorfulness Distribution of the Dataset's Videos.](#contrast-and-colorfulness-distribution-of-the-datasets-videos)
   * [Blockiness and Sharpness Distribution of the Dataset's Videos.](#blockiness-and-sharpness-distribution-of-the-datasets-videos)
   * [Samples of the Dataset Histogram](#samples-of-the-dataset-histogram)
- [Dataset Split](#dataset-split)
   * [Output File](#output-file)
   * [CSV Format](#csv-format)
   * [Required Libraries](#required-libraries)


<br><br>




___
## Dataset Overview
The dataset consists of:
- 80 clips of 10 seconds (600 frames)&nbsp;&nbsp;&nbsp;(~2.33 TB)
- 40 clips of 30 seconds (1800 frames)&nbsp;(~4.25 TB)
- 15 clips of 60 seconds (3600 frames)&nbsp;(~3.20 TB)


<br>
The main dataset directory is broken down as:

<pre>
Dublin  --  <i>main directory accessed through <a href="https://drive.google.com/drive/folders/1vphE2Eg-s-efnLFPShE_WomJXjZjkmlS?usp=sharing">here</a></i>
|
│
└───10sec  --  <i>contains the 10s videos subset <a href="https://drive.google.com/drive/folders/14k8ahFaQ7po0wgeJs0u9jGKzrFnyk0wB?usp=sharing">here</a></i>
│   │
│   └───Analysis  --  <i>Per-frame metric outputs <a href="https://drive.google.com/drive/folders/1MvpLB-lK0Qg2nmkr2zlOo4hxUqGm8FIH?usp=sharing">here</a></i>
│   |   │
|   |   └───encoding_quality  -- <i>encoding quality evalutation of 10s 8K 60fps video files</i>
|   |   |   |
│   |   │   |   120_10sec_8K_enc_qual.csv   
│   |   │   |   121_10sec_8K_enc_qual.csv
│   |   │   |   ...
│   |   │
|   |   └───histograms  -- <i>histogram and hue analysis of 10s 8K 60fps video files</i>
|   |   |   |
│   |   │   |   120_10sec_8K_vid_cmplx.csv
│   |   │   |   121_10sec_8K_vmaf.csv
│   |   │   |   ...
│   |   │
|   |   └───video_complixity  -- <i>pre-frame complexity analysis of 10s 8K 60fps video files</i>
|   |   |   |
│   |   │   |   120_10sec_8K_vmaf.csv
│   |   │   |   121_10sec_8K_vmaf.csv
│   |   │   |   ...
│   |
│   └───Samples  --  <i>4K mid-quality frames extracted for quick viewing <a href="https://drive.google.com/drive/folders/1y3cmiP5j4CNq9JUtkU7Z6X2FbBtoa5wS?usp=sharing">here</a></i>
│   |   │   
│   |   │   120_10s_4K_sample.mp4
│   |   │   121_10s_4K_sample.mp4
│   |   │   ...
│   |
│   └───Videos  --  <i>Raw 10s 8K 60fps video files <a href="https://drive.google.com/drive/folders/1y4y9mS8GR2K2ldFsxA54rcpz4Ltwb34q?usp=sharing">here</a></i>
│       │   
│       │   120_10s_8K.mp4
│       │   121_10s_8K.mp4
│       │   ...
│
└───30sec  --  <i>contains the 30s videos subset <a href="https://drive.google.com/drive/folders/1I7AKk9uTB4x5LfSq863t_-o3jEaLylnB?usp=sharing">here</a></i>
│   │
│   └───Analysis  --  <i>Per-frame metric outputs <a href="https://drive.google.com/drive/folders/1OsDJmgwhwQX6x1GeRFoACli81a5CUbAT?usp=sharing">here</a></i>
│   |   │   
│   |   │   ...
│   |
│   └───Samples  --  <i>4K mid-quality frames extracted for quick viewing <a href="https://drive.google.com/drive/folders/1wH-8-vV3Ahvze_AQrLb0-HQ__CkzP8KJ?usp=sharing">here</a></i>
│   |   │   
│   |   │   ...
│   |
│   └───Videos  --  <i>Raw 30s 8K 60fps video files <a href="https://drive.google.com/drive/folders/1ZtRjndxytEQVcq4sIXr7svjbnYn2HcnZ?usp=sharing">here</a></i>
│       |
│       |   ...
│
└───60sec  --  <i>contains the 60s videos subset <a href="https://drive.google.com/drive/folders/1CIogWGMQFQJGaqJC_tQ6mfc2oqKTlv8J?usp=sharing">here</a></i>
    │
    └───Analysis  --  <i>Per-frame metric outputs <a href="https://drive.google.com/drive/folders/1n4_dKj-gmxm2Q8kCgQ2-DDlAvfm1mEC9?usp=sharing">here</a></i>
    |   │   
    |   │   ...
    │
    └───Samples  --  <i>4K mid-quality frames extracted for quick viewing <a href="https://drive.google.com/drive/folders/1tXiT6eYut_My7ZO1j3hrLn3RMyfuveYy?usp=sharing">here</a></i>
    |   │   
    |   │   ...
    │
    └───Videos  --  <i>Raw 60s 8K 60fps video files <a href="https://drive.google.com/drive/folders/1mismycIhXM3xjNsIvTRgsLiMz31wj0rt?usp=sharing">here</a></i>
        |
        |   ...
</pre>

<br>

### Videos Samples Preview
A snapshot from the first frame of each video is available [here](previews/).
<p float="left">

  <img src="previews\10sec\125_10sec_8K_preview.png" width="19%" />
  <img src="previews\10sec\127_10sec_8K_preview.png" width="19%" /> 
  <img src="previews\10sec\131_10sec_8K_preview.png" width="19%" />
  <img src="previews\10sec\133_10sec_8K_preview.png" width="19%" />
  <img src="previews\10sec\134_10sec_8K_preview.png" width="19%" />
  
  <img src="previews\10sec\136_10sec_8K_preview.png" width="19%" />
  <img src="previews\10sec\143_10sec_8K_preview.png" width="19%" />
  <img src="previews\10sec\145_10sec_8K_preview.png" width="19%" />
  <img src="previews\10sec\147_10sec_8K_preview.png" width="19%" />
  <img src="previews\10sec\148_10sec_8K_preview.png" width="19%" />

  <img src="previews\10sec\159_10sec_8K_preview.png" width="19%" />
  <img src="previews\10sec\165_10sec_8K_preview.png" width="19%" />
  <img src="previews\10sec\171_10sec_8K_preview.png" width="19%" />
  <img src="previews\10sec\193_10sec_8K_preview.png" width="19%" />
  <img src="previews\30sec\040_30sec_8K_preview.png" width="19%" />

  <img src="previews\30sec\043_30sec_8K_preview.png" width="19%" />
  <img src="previews\30sec\046_30sec_8K_preview.png" width="19%" />
  <img src="previews\30sec\047_30sec_8K_preview.png" width="19%" />
  <img src="previews\30sec\052_30sec_8K_preview.png" width="19%" />
  <img src="previews\30sec\074_30sec_8K_preview.png" width="19%" />

  <img src="previews\60sec\034_60sec_8K_preview.png" width="19%" />
  <img src="previews\60sec\038_60sec_8K_preview.png" width="19%" />
  <img src="previews\60sec\040_60sec_8K_preview.png" width="19%" />
  <img src="previews\60sec\041_60sec_8K_preview.png" width="19%" />
  <img src="previews\60sec\044_60sec_8K_preview.png" width="19%" />

</p>

[Back to Top](#idtext)
___
<br><br>

## Dataset Gathering and Generation

The dataset was collected using Nikon Z8 camera with a resolution of 8256 × 4644 at a frame rate of 59.9. The raw footage was captured in 12-bit Nikon N-RAW (NEV) format using BT.2020 color gamut.
Then DaVinci Resolve 19 was used to: 
- a one-time transform from BT.2020/N-Log to DCI-P3/Gamma 2.4 for editability
- cut the videos to uniform lengths and
- crop the videos from the center to a more standard resolution of to 8K DCI (8192 × 4320)
- apply a slight noise filtering in some loww-light cases

The video sequences were exported as 16-bit RGBA lossless PNGs, then FFmpeg with the hardware acceleration library provided by NVIDIA is used to encode the videos using the following command

```bash
ffmpeg -hwaccel cuda -hwaccel_output_format cuda \
    -framerate 60000/1001 -i ".\${seq_id}\%08d.png" \
    -pix_fmt yuv444p16le -c:v hevc_nvenc \
    -tune lossless -profile:v main10 -multipass 2 \
    -bf 4 -b_ref_mode 1 -nonref_p 1 -rc-lookahead 16 \
    ".\${output_file_name}.mp4"
```
[Back to Top](#idtext)

<br>



### Encoding Quality

<p float="left">

  <img src="assets/vmaf_distribution_all.png" width="23%" height="100%"/>
  <img src="assets/ssim_distribution_all.png" width="23%" /> 
  <img src="assets/luma_psnr_distribution_all.png" width="23%" />
  <img src="assets/chroma_psnr_distribution_all.png" width="25%"  height="100%"/>

</p>

*__Figure 5.__ Quality of Encoded Videos Compared to the Source PNGs*

[Back to Top](#idtext)
___
<br><br>

## Dataset Characteristics 

### Spatial and Temporal Perceptual Information Distribution of the Dataset's Videos.
<img src="assets/comparison_main_SI_TI.png" width="49.5%" />

*__Figure 1.__ Spatial and Temporal Information Distribution of the proposed dataset compared to the [VIDEA Dataset](https://github.com/talshoura/VIDEA-8K-60FPS-Dataset)*

[Back to Top](#idtext)
___
<br>

### Average Motion Distribution of the Dataset's Videos.
<img src="assets/comparison_main_AvgMotionXAxis_AvgMotionYAxis.png" width="49.5%" />

*__Figure 2.__ Average Motion Distribution Distribution of the proposed dataset compared to the [VIDEA Dataset](https://github.com/talshoura/VIDEA-8K-60FPS-Dataset)*

[Back to Top](#idtext)
___
<br>

### Contrast and Colorfulness Distribution of the Dataset's Videos.
<img src="assets/comparison_main_Contrast_Colorfulness.png" width="49.5%" />

*__Figure 3.__ Spatial and Temporal Information Distribution of the proposed dataset compared to the [VIDEA Dataset](https://github.com/talshoura/VIDEA-8K-60FPS-Dataset)*

[Back to Top](#idtext)
___
<br>

### Blockiness and Sharpness Distribution of the Dataset's Videos.
<img src="assets/comparison_main_Blockiness_Sharpness.png" width="49.5%" />

*__Figure 4.__ Spatial and Temporal Information Distribution of the proposed dataset compared to the [VIDEA Dataset](https://github.com/talshoura/VIDEA-8K-60FPS-Dataset)*

[Back to Top](#idtext)
___
<br>


### Samples of the Dataset Histogram
The full list of the histograms is available [here](histograms/) as images and in the database as csv files
<p float="left">

  <img src="histograms\60sec\039_60sec_histogram.png" width="49.5%" />
  <img src="histograms\60sec\039_60sec_saturation.png" width="49.5%" />

  <img src="histograms\10sec\199_10sec_histogram.png" width="49.5%" />
  <img src="histograms\10sec\199_10sec_saturation.png" width="49.5%" />

  <img src="histograms\30sec\058_30sec_histogram.png" width="49.5%" />
  <img src="histograms\30sec\058_30sec_saturation.png" width="49.5%" />

  <img src="histograms\10sec\152_10sec_histogram.png" width="49.5%" />
  <img src="histograms\10sec\152_10sec_saturation.png" width="49.5%" />

  <img src="histograms\10sec\157_10sec_histogram.png" width="49.5%" />
  <img src="histograms\10sec\157_10sec_saturation.png" width="49.5%" />

</p>

*__Figure 5.__ Sample of Histograms and Hue Satuaration across Videos*

[Back to Top](#idtext)
___
<br>

## Dataset Split

To ensure a fair and cluster-representative train/test division, videos were clustered using **Agglomerative Clustering** based on statistical features (e.g., mean, skewness, kurtosis, etc.). The resulting clusters were used to **stratify** the data before splitting.

- **Clustering algorithm**: `AgglomerativeClustering (n_clusters=12)`
- **Stratified by**: Cluster labels
- **Split ratio**: `80%` train / `20%` test
- **Random seed**: `0` (for reproducibility)

### Output File
The mapping of each video to its dataset split is stored in:


### CSV Format

| Column         | Description                           |
|----------------|---------------------------------------|
| `video_number` | Unique name/ID of the video           |
| `cluster`      | Cluster ID based on UMAP              |
| `split`        | One of `train` or `test`              |


**Example:**
```csv
video_number,cluster,split
120_10s,4,test
121_10s,3,train
122_10s,4,test
```


### Required Libraries

The following Python packages are required to run the clustering and dataset splitting pipeline:

```bash
pip install pandas scikit-learn umap-learn matplotlib
```

Please refer to [train_test_split/](train_test_split/) for the code and csv files.

[Back to Top](#idtext)
___
<br>












