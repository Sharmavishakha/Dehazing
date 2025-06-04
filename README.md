This project presents a novel approach to image dehazing, using a pixel-level analysis of haze-related parameters such as scattering coefficient, atmospheric light (A), and transmission estimation. The system iteratively enhances the image quality while maintaining structural integrity using SSIM-based evaluation. The technique is currently in its final phase of publication as a research paper.

# 🧠 Motivation
Hazy images often suffer from low contrast, faded colors, and visual distortion — posing challenges in computer vision applications like autonomous navigation, surveillance, and remote sensing. This project proposes a mathematically grounded and iterative method to restore clarity using a physically-inspired haze model at a per-pixel level.

# 📸 Methodology Overview
The approach is grounded in the Koschmieder’s atmospheric scattering model:

I(x) = J(x) * t(x) + A * (1 - t(x))

Where:

I(x) = observed hazy image

J(x) = scene radiance (clean image)

t(x) = transmission map

A = global atmospheric light

# 🔍 Key Components
Pixel-wise Parameter Estimation

Scattering Coefficient (β): Estimated using intensity gradients and local contrast.

Transmission Map (t(x)): Derived per pixel using β and scene depth approximation.

Atmospheric Light (A): Dynamically calculated using brightest regions in the haze-dominant zones.

Iterative Dehazing Loop

Each iteration progressively updates the pixel values.

SSIM (Structural Similarity Index) is computed to determine convergence and stop criteria.

# 🧪 Results
<img width="608" alt="dehazing" src="https://github.com/user-attachments/assets/7db5665c-44be-4e8d-a0a7-b28d5721c798" />

Improved visibility and contrast

Preserved texture and structure (validated via SSIM = 0.988)

Enhanced performance in downstream vision tasks (e.g., edge detection)
