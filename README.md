# GPU-Accelerated Grayscale Image Conversion Using CUDA

## Overview

This capstone project demonstrates the use of CUDA for accelerating the process of converting color (RGB) images to grayscale. The project utilizes NVIDIA's GPU architecture to parallelize pixel-wise computations, dramatically improving performance over CPU-based equivalents. It showcases foundational CUDA programming, image processing, and performance verification techniques.

## How It Works

The program loads a JPEG image and uses a CUDA kernel to convert each pixel from RGB to grayscale using the NTSC-recommended formula:

```
Gray = 0.299 * Red + 0.587 * Green + 0.114 * Blue
```

### GPU Kernel

The CUDA kernel implemented in `student_func.cu` handles the parallel processing of image pixels. It maps each thread to an image pixel, ensuring high throughput for large images.

## Repository Contents

- `main.cpp` – Main entry point for the application.
- `student_func.cu` – Custom CUDA kernel for RGB to grayscale conversion.
- `compare.cpp` and `compare.h` – Utility to compare generated output with reference images.
- `utils.h`, `timer.h` – Support utilities.
- `Makefile.txt`, `CMakeLists.txt` – For building the project.
- Input & output images for testing and validation.

## Installation

### Requirements

- CUDA Toolkit (tested on CUDA 11+)
- CMake or Make
- NVIDIA GPU with compute capability 3.0+

### Compilation

```bash
make
# or with cmake
cmake .
make
```

## Running the Program

```bash
./main cinque_terre_small.jpg
```

This reads the input image, runs the grayscale conversion on the GPU, and generates the following output files:
- `HW1_output.png` – GPU-generated grayscale image.
- `HW1_reference.png` – CPU-based reference output.
- `HW1_differenceImage.png` – Visual difference between GPU and reference outputs.

## Outputs

### Input Image

![image](https://github.com/DeepanshuDabas03/Peer-graded-Assignment-GPU-Specialization-Capstone-Project/blob/main/cinque_terre_small.jpg)
### GPU Output

![Grayscale Output](HW1_output.png)

### Reference Output

![Reference Output](HW1_reference.png)

### Difference Image

![Difference Analysis](HW1_differenceImage.png)

## Project Goals

This project serves as a personal exploration into real-time image processing using parallel programming with CUDA. The experience builds foundational GPU programming skills, focusing on memory management, kernel launches, and validation.

## Lessons Learned

- Effective memory coalescing is critical for GPU performance.
- CUDA streams and shared memory can offer further performance gains.
- Validation against a reference image helps catch edge-case discrepancies in parallel computations.

## Future Work

- Extend to support video frame conversion.
- Add real-time webcam stream grayscale conversion.
- Benchmark CUDA performance against OpenCV CPU and GPU implementations.


---

*Author: [Your Name]*  
*Course: CUDA Programming Specialization – Capstone Project*


# GPU-Capstone
## Color to Greyscale Conversion
### Converted RGBA image to greyscale using the formula recommended by the NTSC.

![image](https://github.com/DeepanshuDabas03/Peer-graded-Assignment-GPU-Specialization-Capstone-Project/blob/main/HW1_output.png)
![image](https://github.com/DeepanshuDabas03/Peer-graded-Assignment-GPU-Specialization-Capstone-Project/blob/main/HW1_reference.png)
![image](https://github.com/DeepanshuDabas03/Peer-graded-Assignment-GPU-Specialization-Capstone-Project/blob/main/HW1_differenceImage.png)

![image](https://github.com/user-attachments/assets/a54b8c99-e6e9-415f-b4a0-23f00826da9d)

