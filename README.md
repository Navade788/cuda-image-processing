# CUDA Image Processing at Scale

## Project Overview

This project demonstrates GPU-accelerated image processing using CUDA C++. The application processes a large collection of images using CUDA kernels executed on an NVIDIA GPU. The primary goal of the project is to showcase how parallel processing with CUDA can significantly improve the performance of image processing workloads compared to traditional CPU-based execution.

The program performs image transformations such as grayscale conversion, blur filtering, and edge detection on hundreds of images. Each CUDA thread processes image pixels in parallel, allowing the system to efficiently handle large-scale image datasets.

This project was developed as part of the CUDA at Scale Independent Project assignment.

---

# Objectives

The main objectives of this project are:

- Demonstrate GPU-based parallel image processing
- Use CUDA kernels for image transformations
- Process large volumes of image data efficiently
- Explore CUDA memory management techniques
- Compare GPU computation with traditional sequential processing
- Build a scalable image-processing pipeline

---

# Features

The project includes the following GPU-accelerated image processing operations:

## Grayscale Conversion
Converts RGB images into grayscale using CUDA kernels.

## Blur Filtering
Applies blur filters to smooth image details.

## Edge Detection
Detects image edges using pixel intensity gradients.

## Batch Processing
Processes hundreds of images automatically in sequence.

## CUDA Parallelism
Each CUDA thread handles individual pixel operations simultaneously.

---

# Technologies Used

- CUDA C++
- NVIDIA CUDA Toolkit
- C++
- GPU Kernels
- Parallel Computing
- Linux Environment
- Makefile Build System

---

# System Requirements

## Hardware
- NVIDIA GPU with CUDA support

## Software
- CUDA Toolkit
- GCC Compiler
- Linux OS
- nvcc Compiler

---

# Project Structure

```text
cuda-image-processing/
│
├── main.cu
├── image_kernels.cu
├── image_kernels.h
├── Makefile
├── run.sh
├── README.md
│
├── input_images/
│   ├── image1.png
│   ├── image2.png
│   └── ...
│
├── output_images/
│   ├── grayscale/
│   ├── blur/
│   └── edges/
│
├── logs/
│   └── execution_log.txt
│
├── screenshots/
│   ├── before_processing.png
│   ├── after_processing.png
│   └── terminal_output.png
│
└── artifacts/
    ├── before_after_examples/
    └── benchmark_results/
```

---

# CUDA Concepts Demonstrated

This project demonstrates several important CUDA programming concepts:

- CUDA kernels
- Parallel thread execution
- Grid and block configuration
- Device memory allocation
- Memory transfer between CPU and GPU
- Thread indexing
- Kernel synchronization
- GPU-based computation

---

# Workflow

The application follows this workflow:

1. Load input images from storage
2. Allocate device memory
3. Copy image data to GPU memory
4. Launch CUDA kernels
5. Process pixels in parallel
6. Copy processed output back to CPU memory
7. Save transformed images
8. Repeat for all images in dataset

---

# Parallel Processing Design

Each CUDA thread processes one or more pixels independently.

Example:
- Thread 0 → Pixel 0
- Thread 1 → Pixel 1
- Thread 2 → Pixel 2

This massively parallel structure allows the GPU to process thousands of pixels simultaneously.

---

# Memory Management

The following CUDA memory operations are used:

```cpp
cudaMalloc()
cudaMemcpy()
cudaFree()
```

Memory is allocated on the GPU for:
- Input image buffers
- Output image buffers
- Temporary filter data

---

# Compilation Instructions

## Using Makefile

```bash
make
```

## Manual Compilation

```bash
nvcc main.cu image_kernels.cu -o image_processor
```

---

# Execution Instructions

Run the program:

```bash
./image_processor
```

Or:

```bash
bash run.sh
```

---

# Command Line Arguments

The program supports command line arguments for selecting filters and directories.

Example:

```bash
./image_processor input_images/ output_images/ grayscale
```

Arguments:
- Input directory
- Output directory
- Filter type

Supported filters:
- grayscale
- blur
- edge

---

# Sample Output

```text
Processing image1.png ...
Launching CUDA kernel ...
Completed grayscale conversion.

Processing image2.png ...
Launching CUDA kernel ...
Completed blur filter.

Total images processed: 150
Execution completed successfully.
```

---

# Proof of Execution

The repository includes execution artifacts demonstrating successful GPU execution:

- Terminal execution logs
- Before and after images
- Output screenshots
- Processed image datasets
- Batch processing examples

These files are located in:
- `logs/`
- `screenshots/`
- `artifacts/`

---

# Performance Benefits

GPU parallel processing significantly improves throughput when processing large image datasets.

Advantages include:
- Faster pixel computation
- Massive parallel execution
- Better scalability
- Reduced processing time

---

# Challenges Faced

Several challenges were encountered during development:

- Managing GPU memory efficiently
- Optimizing thread/block configuration
- Handling large datasets
- Synchronizing CPU and GPU operations
- Debugging CUDA kernels
- Preventing invalid memory access

---

# Future Improvements

Potential future enhancements include:

- Shared memory optimization
- Multi-GPU support
- Real-time video processing
- Advanced image filters
- CUDA stream optimization
- AI-based image enhancement
- OpenCV CUDA integration

---

# Educational Outcomes

This project provided practical experience with:

- CUDA programming
- GPU acceleration
- Parallel algorithm design
- Device memory management
- High-performance computing
- Batch image processing

It also demonstrated how GPUs can accelerate real-world image-processing applications.

---

# Screenshots

The `screenshots/` folder contains:
- Input image examples
- Output image examples
- Execution terminal screenshots
- CUDA execution results

---

# Execution Artifacts

The repository also includes:
- Execution logs
- Sample outputs
- Benchmark examples
- Before/after comparisons

These artifacts prove successful GPU execution on large image datasets.

---

# References

- NVIDIA CUDA Documentation
- CUDA C++ Programming Guide
- USC SIPI Image Database
- CUDA Best Practices Guide

---

# Author

Navadeep

---

# License

This project is developed for educational purposes as part of the CUDA at Scale Independent Project assignment.
