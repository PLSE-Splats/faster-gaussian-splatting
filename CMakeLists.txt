cmake_minimum_required(VERSION 4.2)
project(FasterGS CUDA)

set(CMAKE_CXX_STANDARD 17)

include_directories(FasterGSCudaBackend/FasterGSCudaBackend/adam/include)
include_directories(FasterGSCudaBackend/FasterGSCudaBackend/densification/include)
include_directories(FasterGSCudaBackend/FasterGSCudaBackend/filter3d/include)
include_directories(FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include)
include_directories(FasterGSCudaBackend/FasterGSCudaBackend/utils)

add_executable(FasterGS
        FasterGSCudaBackend/FasterGSCudaBackend/adam/include/adam.h
        FasterGSCudaBackend/FasterGSCudaBackend/adam/include/adam_config.h
        FasterGSCudaBackend/FasterGSCudaBackend/adam/src/adam.cu
        FasterGSCudaBackend/FasterGSCudaBackend/densification/include/densification_api.h
        FasterGSCudaBackend/FasterGSCudaBackend/densification/include/densification_config.h
        FasterGSCudaBackend/FasterGSCudaBackend/densification/include/kernels_mcmc.cuh
        FasterGSCudaBackend/FasterGSCudaBackend/densification/include/mcmc.h
        FasterGSCudaBackend/FasterGSCudaBackend/densification/src/densification_api.cu
        FasterGSCudaBackend/FasterGSCudaBackend/densification/src/mcmc.cu
        FasterGSCudaBackend/FasterGSCudaBackend/filter3d/include/filter3d.h
        FasterGSCudaBackend/FasterGSCudaBackend/filter3d/include/filter3d_config.h
        FasterGSCudaBackend/FasterGSCudaBackend/filter3d/src/filter3d.cu
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include/backward.h
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include/buffer_utils.h
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include/forward.h
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include/inference.h
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include/kernel_utils.cuh
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include/kernels_backward.cuh
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include/kernels_forward.cuh
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include/kernels_inference.cuh
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include/kernels_pruning_scores.cuh
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include/pruning_scores.h
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include/rasterization_api.h
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include/rasterization_config.h
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/include/sh_utils.cuh
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/src/backward.cu
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/src/forward.cu
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/src/inference.cu
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/src/pruning_scores.cu
        FasterGSCudaBackend/FasterGSCudaBackend/rasterization/src/rasterization_api.cu
        FasterGSCudaBackend/FasterGSCudaBackend/torch_bindings/bindings.cpp
        FasterGSCudaBackend/FasterGSCudaBackend/utils/helper_math.h
        FasterGSCudaBackend/FasterGSCudaBackend/utils/torch_utils.h
        FasterGSCudaBackend/FasterGSCudaBackend/utils/utils.h)
