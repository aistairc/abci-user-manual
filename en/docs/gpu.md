# 7. GPU

The following libraries provided by NVIDIA are available on the ABCI System:

* [CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit)
* [NVIDIA CUDA Deep Neural Network library (cuDNN)](https://developer.nvidia.com/cudnn)
* [NVIDIA Collective Communications Library (NCCL)](https://developer.nvidia.com/nccl)
* [GDRCopy: A fast GPU memory copy library based on NVIDIA GPUDirect RDMA technology](https://github.com/NVIDIA/gdrcopy)

To use these libraries, it is necessary to set up the users environment using the `module` command in advance. The `module` command allows users to automatically set environment variables for execution, such as` PATH`, and environment variables for compilation, such as search paths for header files and libraries.

```
[username@g0001 ~]$ module load cuda/10.0/10.0.130.1
[username@g0001 ~]$ module load cudnn/7.4/7.4.2
[username@g0001 ~]$ module load nccl/2.4/2.4.8-1
```

The following is a list of CUDA Toolkit, cuDNN, and NCCL that can be used with the ABCI system.

## CUDA Toolkit

<!--
| Major version | Minor version | Available from NVIDIA | Installed on ABCI | Provided with `module` |
|:--|:--|:--|:--|:--|
| cuda/8.0  | 8.0.44     | Yes | -   | -   |
| cuda/8.0  | 8.0.61     | Yes | -   | -   |
| cuda/8.0  | 8.0.61.2   | Yes | Yes | Yes |
| cuda/9.0  | 9.0.176    | Yes | Yes | Yes |
| cuda/9.0  | 9.0.176.1  | Yes | Yes | -   |
| cuda/9.0  | 9.0.176.2  | Yes | Yes | -   |
| cuda/9.0  | 9.0.176.3  | Yes | Yes | -   |
| cuda/9.0  | 9.0.176.4  | Yes | Yes | Yes |
| cuda/9.1  | 9.1.85     | Yes | -   | -   |
| cuda/9.1  | 9.1.85.1   | Yes | -   | -   |
| cuda/9.1  | 9.1.85.2   | Yes | -   | -   |
| cuda/9.1  | 9.1.85.3   | Yes | Yes | Yes |
| cuda/9.2  | 9.2.88.1   | -   | Yes | Yes |
| cuda/9.2  | 9.2.148    | Yes | Yes | -   |
| cuda/9.2  | 9.2.148.1  | Yes | Yes | Yes |
| cuda/10.0 | 10.0.130   | Yes | Yes | Yes |
| cuda/10.0 | 10.0.130.1 | Yes | Yes | Yes |
| cuda/10.1 | 10.1.105   | Yes | -   | -   |
| cuda/10.1 | 10.1.168   | Yes | Yes | -   |
| cuda/10.1 | 10.1.243   | Yes | Yes | Yes |
| cuda/10.2 | 10.2.89    | Yes | Yes | Yes |
-->

| Major version | Minor version | Available from NVIDIA | Available on Compute Node (V) | Available on Compute Node (A) |
|:--|:--|:--|:--|:--|
| cuda/8.0 | 8.0.44      | Yes | -   | -   |
| cuda/8.0 | 8.0.61      | Yes | -   | -   |
| cuda/8.0 | 8.0.61.2    | Yes | Yes | -   |
| cuda/9.0 | 9.0.176     | Yes | Yes | -   |
| cuda/9.0 | 9.0.176.1   | Yes | -   | -   |
| cuda/9.0 | 9.0.176.2   | Yes | -   | -   |
| cuda/9.0 | 9.0.176.3   | Yes | -   | -   |
| cuda/9.0 | 9.0.176.4   | Yes | Yes | -   |
| cuda/9.1 | 9.1.85      | Yes | -   | -   |
| cuda/9.1 | 9.1.85.1    | Yes | -   | -   |
| cuda/9.1 | 9.1.85.2    | Yes | -   | -   |
| cuda/9.1 | 9.1.85.3    | Yes | Yes | -   |
| cuda/9.2 | 9.2.88.1    | -   | Yes | -   |
| cuda/9.2 | 9.2.148     | Yes | -   | -   |
| cuda/9.2 | 9.2.148.1   | Yes | Yes | -   |
| cuda/10.0 | 10.0.130   | Yes | -   | -   |
| cuda/10.0 | 10.0.130.1 | Yes | Yes | Yes[^1] |
| cuda/10.1 | 10.1.105   | Yes | -   | -   |
| cuda/10.1 | 10.1.168   | Yes | -   | -   |
| cuda/10.1 | 10.1.243   | Yes | Yes | Yes[^1] |
| cuda/10.2 | 10.2.89    | Yes | Yes | Yes[^1] |
| cuda/11.0 | 11.0.2     | Yes | -   | -   |
| cuda/11.0 | 11.0.3     | Yes | Yes | Yes |
| cuda/11.1 | 11.1.0     | Yes | -   | -   |
| cuda/11.1 | 11.1.1     | Yes | Yes | Yes |
| cuda/11.2 | 11.2.0     | Yes | -   | -   |
| cuda/11.2 | 11.2.1     | Yes | -   | -   |
| cuda/11.2 | 11.2.2     | Yes | Yes | Yes |

[^1]: Provided only for experimental use. NVIDIA A100 is supported on CUDA 11＋.

## cuDNN

<!--
| Version | cuda/8.0 | cuda/9.0 | cuda/9.1 | cuda/9.2 | cuda/10.0 | cuda/10.1 | cuda/10.2 | cuda/11.0 | cuda/11.1 | cuda/11.2 | cuda/11.3 |
|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|
| 5.1.10 | Yes | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |
| 6.0.21 | Yes | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |
| 7.0.5  | Yes | Yes | Yes | -   | -   | -   | -   | -   | -   | -   | -   |
| 7.1.3  | Yes | Yes | Yes | -   | -   | -   | -   | -   | -   | -   | -   |
| 7.1.4  | -   | Yes | -   | Yes | -   | -   | -   | -   | -   | -   | -   |
| 7.2.1  | \*1 | Yes | -   | Yes | -   | -   | -   | -   | -   | -   | -   |
| 7.3.0  | -   | \*1 | -   | -   | \*1 | -   | -   | -   | -   | -   | -   |
| 7.3.1  | -   | Yes | -   | Yes | Yes | -   | -   | -   | -   | -   | -   |
| 7.4.1  | -   | \*1 | -   | \*1 | \*1 | -   | -   | -   | -   | -   | -   |
| 7.4.2  | -   | Yes | -   | Yes | Yes | -   | -   | -   | -   | -   | -   |
| 7.5.0  | -   | Yes | -   | Yes | Yes | Yes | -   | -   | -   | -   | -   |
| 7.5.1  | -   | Yes | -   | Yes | Yes | Yes | -   | -   | -   | -   | -   |
| 7.6.0  | -   | Yes | -   | Yes | Yes | Yes | -   | -   | -   | -   | -   |
| 7.6.1  | -   | Yes | -   | Yes | Yes | Yes | -   | -   | -   | -   | -   |
| 7.6.2  | -   | Yes | -   | Yes | Yes | Yes | -   | -   | -   | -   | -   |
| 7.6.3  | -   | Yes | -   | Yes | Yes | Yes | -   | -   | -   | -   | -   |
| 7.6.4  | -   | Yes | -   | Yes | Yes | Yes | -   | -   | -   | -   | -   |
| 7.6.5  | -   | Yes | -   | Yes | Yes | Yes | Yes | -   | -   | -   | -   |
| 8.0.2  | -   | -   | -   | -   | -   | Yes | Yes | -   | -   | -   | -   |
| 8.0.5  | -   | -   | -   | -   | -   | Yes | Yes | Yes | Yes | -   | -   |
| 8.1.1  | -   | -   | -   | -   | -   | -   | Yes | Yes | Yes | Yes | -   |
| 8.2.0  | -   | -   | -   | -   | -   | -   | Yes | Yes | Yes | Yes | Yes |

\*1 Installed, but modules are not provided
\*2 Installed, but not yet supported
-->

Compute Node (V):

| Version | cuda/8.0 | cuda/9.0 | cuda/9.1 | cuda/9.2 | cuda/10.0 | cuda/10.1 | cuda/10.2 | cuda/11.0 | cuda/11.1 | cuda/11.2 |
|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|
| 5.1.10 | Yes | -   | -   | -   | -   | -   | -   | -   | -   | -   |
| 6.0.21 | Yes | -   | -   | -   | -   | -   | -   | -   | -   | -   |
| 7.0.5  | Yes | Yes | Yes | -   | -   | -   | -   | -   | -   | -   |
| 7.1.4  | -   | Yes | -   | Yes | -   | -   | -   | -   | -   | -   |
| 7.2.1  | -   | Yes | -   | Yes | -   | -   | -   | -   | -   | -   |
| 7.3.0  | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |
| 7.3.1  | -   | Yes | -   | Yes | Yes | -   | -   | -   | -   | -   |
| 7.4.2  | -   | Yes | -   | Yes | Yes | -   | -   | -   | -   | -   |
| 7.5.1  | -   | Yes | -   | Yes | Yes | Yes | -   | -   | -   | -   |
| 7.6.5  | -   | Yes | -   | Yes | Yes | Yes | Yes | -   | -   | -   |
| 8.0.5  | -   | -   | -   | -   | -   | Yes | Yes | Yes | Yes | -   |
| 8.1.1  | -   | -   | -   | -   | -   | -   | Yes | Yes | Yes | Yes |
| 8.2.0  | -   | -   | -   | -   | -   | -   | Yes | Yes | Yes | Yes |

Compute Node (A):

| Version | cuda/10.0[^1] | cuda/10.1[^1] | cuda/10.2[^1] | cuda/11.0 | cuda/11.1 | cuda/11.2 |
|:--|:--|:--|:--|:--|:--|:--|
| 7.3.1  | Yes | -   | -   | -   | -   | -   |
| 7.4.2  | Yes | -   | -   | -   | -   | -   |
| 7.5.1  | Yes | Yes | -   | -   | -   | -   |
| 7.6.5  | Yes | Yes | Yes | -   | -   | -   |
| 8.0.5  | -   | Yes | Yes | Yes | Yes | -   |
| 8.1.1  | -   | -   | Yes | Yes | Yes | Yes |
| 8.2.0  | -   | -   | Yes | Yes | Yes | Yes |

## NCCL

<!--
| Version | cuda/8.0 | cuda/9.0 | cuda/9.1 | cuda/9.2 | cuda/10.0 | cuda/10.1 | cuda/10.2 | cuda/11.0 | cuda/11.1 | cuda/11.2 | cuda/11.3 |
|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|
| 1.3.5-1  | Yes | Yes | Yes | Yes | Yes | -   | -   | -   | -   | -   | -   |
| 2.0.5-3  | \*1 | \*1 | -   | -   | -   | -   | -   | -   | -   | -   | -   |
| 2.1.15-1 | Yes | Yes | Yes | -   | -   | -   | -   | -   | -   | -   | -   |
| 2.2.12-1 | \*1 | \*1 | -   | \*1 | -   | -   | -   | -   | -   | -   | -   |
| 2.2.13-1 | Yes | Yes | -   | Yes | -   | -   | -   | -   | -   | -   | -   |
| 2.3.4-1  | -   | Yes | -   | Yes | Yes | -   | -   | -   | -   | -   | -   |
| 2.3.5-2  | -   | Yes | -   | Yes | Yes | -   | -   | -   | -   | -   | -   |
| 2.3.7-1  | -   | Yes | -   | Yes | Yes | -   | -   | -   | -   | -   | -   |
| 2.4.2-1  | -   | -   | -   | Yes | Yes | Yes | -   | -   | -   | -   | -   |
| 2.4.7-1  | -   | -   | -   | Yes | Yes | Yes | -   | -   | -   | -   | -   |
| 2.4.8-1  | -   | -   | -   | Yes | Yes | Yes | -   | -   | -   | -   | -   |
| 2.5.6-1  | -   | Yes | -   | -   | Yes | Yes | Yes | -   | -   | -   | -   |
| 2.6.4-1  | -   | -   | -   | -   | Yes | Yes | Yes | -   | -   | -   | -   |
| 2.7.8-1  | -   | -   | -   | -   | -   | Yes | Yes | Yes | Yes | -   | -   |
| 2.8.3-1  | -   | -   | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | -   |
| 2.8.4-1  | -   | -   | -   | -   | -   | -   | Yes | Yes | Yes | Yes | -   |
| 2.9.6-1  | -   | -   | -   | -   | -   | -   | Yes | Yes | -   | -   | Yes |

\*1 Installed, but modules are not provided
\*2 Installed, but not yet supported
-->

Compute Node (V):

| Version | cuda/8.0 | cuda/9.0 | cuda/9.1 | cuda/9.2 | cuda/10.0 | cuda/10.1 | cuda/10.2 | cuda/11.0 | cuda/11.1 | cuda/11.2 |
|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|
| 1.3.5-1  | Yes | Yes | Yes | Yes | Yes | -   | -   | -   | -   | -   |
| 2.1.15-1 | Yes | Yes | Yes | -   | -   | -   | -   | -   | -   | -   |
| 2.2.13-1 | Yes | Yes | -   | Yes | -   | -   | -   | -   | -   | -   |
| 2.3.7-1  | -   | Yes | -   | Yes | Yes | -   | -   | -   | -   | -   |
| 2.4.8-1  | -   | -   | -   | Yes | Yes | Yes | -   | -   | -   | -   |
| 2.5.6-1  | -   | Yes | -   | -   | Yes | Yes | Yes | -   | -   | -   |
| 2.6.4-1  | -   | -   | -   | -   | Yes | Yes | Yes | -   | -   | -   |
| 2.7.8-1  | -   | -   | -   | -   | -   | Yes | Yes | Yes | Yes | -   |
| 2.8.4-1  | -   | -   | -   | -   | -   | -   | Yes | Yes | Yes | Yes |
| 2.9.6-1  | -   | -   | -   | -   | -   | -   | Yes | Yes | -   | -   |

Compute Node (A):

| Version | cuda/10.0[^1] | cuda/10.1[^1] | cuda/10.2[^1] | cuda/11.0 | cuda/11.1 | cuda/11.2 |
|:--|:--|:--|:--|:--|:--|:--|
| 2.3.7-1  | Yes | -   | -   | -   | -   | -   |
| 2.4.8-1  | Yes | Yes | -   | -   | -   | -   |
| 2.5.6-1  | Yes | Yes | Yes | -   | -   | -   |
| 2.6.4-1  | Yes | Yes | Yes | -   | -   | -   |
| 2.7.8-1  | -   | Yes | Yes | Yes | Yes | -   |
| 2.8.4-1  | -   | -   | Yes | Yes | Yes | Yes |
| 2.9.6-1  | -   | -   | Yes | Yes | -   | -   |

## GDRCopy

Compute Node (V):

| Version | cuda/8.0 | cuda/9.0 | cuda/9.1 | cuda/9.2 | cuda/10.0 | cuda/10.1 | cuda/10.2 | cuda/11.0 | cuda/11.1 | cuda/11.2 |
|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|
| 2.0 | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes |

Compute Node (A):

| Version | cuda/10.0 | cuda/10.1 | cuda/10.2 | cuda/11.0 | cuda/11.1 | cuda/11.2 |
|:--|:--|:--|:--|:--|:--|:--|
| 2.1 | Yes | Yes | Yes | Yes | Yes | Yes |

## Changing GPU Compute Mode {#changing-gpu-compute-mode}

You can change GPU Compute Mode by using `-v GPU_COMPUTE_MODE=num` option. The following three Compute Modes can be specified.

| Option | Description |
|:--|:--|
|-v GPU\_COMPUTE\_MODE=0 | DEFAULT mode.<br>Multiple contexts are allowed per device. |
|-v GPU\_COMPUTE\_MODE=1 | EXCLUSIVE\_PROCESS mode.<br>Only one context is allowed per device, usable from multiple threads at a time. |
|-v GPU\_COMPUTE\_MODE=2 | PROHIBITED mode.<br>No contexts are allowed per device (no compute apps). |

Execution example in an interactive job:

```
[username@es1 ~]$ qrsh -g grpname -l rt_F=1 -l h_rt=1:00:00 -v GPU_COMPUTE_MODE=1
```

Execution example in a batch job:

```bash
#!/bin/bash

#$ -l rt_F=1
#$ -l h_rt=1:00:00
#$ -j y
#$ -cwd
#$ -v GPU_COMPUTE_MODE=1
/usr/bin/nvidia-smi
```
