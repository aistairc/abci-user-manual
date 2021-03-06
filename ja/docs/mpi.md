# MPI

ABCIシステムでは、以下のMPIを利用できます。

* [Open MPI](https://www.open-mpi.org/)
* [MVAPICH2](http://mvapich.cse.ohio-state.edu/overview/#mv2)
* [MVAPICH2-GDR](http://mvapich.cse.ohio-state.edu/overview/#mv2gdr)
* [Intel MPI](https://software.intel.com/en-us/intel-mpi-library)

利用するためには事前に`module`コマンドを用いて利用環境を設定する必要があります。
インタラクティブノードで`module`コマンドを用いると、コンパイル用環境変数（ヘッダファイルおよびライブラリのサーチパス）が自動で設定されます。
計算ノードで`module`コマンドを用いると、コンパイル用環境変数に加え、実行用環境変数も自動で設定されます。

```
[username@es1 ~]$ module load openmpi/4.0.5
```

```
[username@es1 ~]$ module load cuda/11.0 mvapich/mvapich2-gdr/2.3.5
```

```
[username@es1 ~]$ module load mvapich/mvapich2/2.3.5
```

```
[username@es1 ~]$ module load intel-mpi/2019.9
```

以下では、ABCIシステムに導入されているMPIのバージョン一覧を示します。

## Open MPI

計算ノード(V):

| openmpi/ | Compiler version | w/o CUDA | cuda8.0 | cuda9.0 | cuda9.1 | cuda9.2 | cuda10.0 | cuda10.1 | cuda10.2 | cuda11.0 | cuda11.1 | cuda11.2 |
|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|
| 2.1.6  | gcc/4.8.5     | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 2.1.6  | gcc/7.4.0     | Yes | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 2.1.6  | gcc/9.3.0     | Yes | -   | -   | -   | -   | -   | Yes | Yes | Yes | Yes | Yes |
| 2.1.6  | pgi/20.4      | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 2.1.6  | nvhpc/20.11   | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 2.1.6  | nvhpc/21.2    | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 3.1.6  | gcc/4.8.5     | Yes | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 3.1.6  | gcc/7.4.0     | Yes | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 3.1.6  | gcc/9.3.0     | Yes | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 3.1.6  | pgi/20.4      | Yes | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 3.1.6  | nvhpc/20.11   | Yes | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 3.1.6  | nvhpc/21.2    | Yes | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 4.0.5  | gcc/4.8.5     | Yes | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 4.0.5  | gcc/7.4.0     | Yes | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 4.0.5  | gcc/9.3.0     | Yes | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 4.0.5  | pgi/20.4      | Yes | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 4.0.5  | nvhpc/20.11   | Yes | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 4.0.5  | nvhpc/21.2    | Yes | -   | -   | -   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |

計算ノード(A):

| openmpi/ | Compiler version | w/o CUDA | cuda10.0[^1] | cuda10.1[^1] | cuda10.2[^1] | cuda11.0 | cuda11.1 | cuda11.2 |
|:--|:--|:--|:--|:--|:--|:--|:--|:--|
| 2.1.6  | gcc/7.4.0     | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 2.1.6  | gcc/8.3.1     | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 2.1.6  | gcc/9.3.0     | Yes | -   | Yes | Yes | Yes | Yes | Yes |
| 2.1.6  | pgi/20.4      | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 2.1.6  | nvhpc/20.11   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 2.1.6  | nvhpc/21.2    | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 3.1.6  | gcc/7.4.0     | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 3.1.6  | gcc/8.3.1     | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 3.1.6  | gcc/9.3.0     | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 3.1.6  | pgi/20.4      | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 3.1.6  | nvhpc/20.11   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 3.1.6  | nvhpc/21.2    | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 4.0.5  | gcc/7.4.0     | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 4.0.5  | gcc/8.3.1     | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 4.0.5  | gcc/9.3.0     | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 4.0.5  | pgi/20.4      | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 4.0.5  | nvhpc/20.11   | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| 4.0.5  | nvhpc/21.2    | Yes | Yes | Yes | Yes | Yes | Yes | Yes |

[^1]: 試験用に提供しています。NVIDIA A100は、CUDA 11以降でサポートされます。

## MVAPICH2

| mvapich/mvapich2/ | Compiler version | Compute Node (V) | Compute Node (A) |
|:--|:--|:--|:--|
| 2.3.5 | gcc/4.8.5     | Yes | -   |
| 2.3.5 | gcc/7.4.0     | Yes | Yes |
| 2.3.5 | gcc/8.3.1     | -   | Yes |
| 2.3.5 | gcc/9.3.0     | Yes | Yes |
| 2.3.5 | pgi/20.4      | Yes | Yes |
| 2.3.5 | nvhpc/20.11   | Yes | Yes |
| 2.3.5 | nvhpc/21.2    | Yes | Yes |

## MVAPICH2-GDR

| mvapich/mvapich2-gdr/ | Compiler version | cuda10.0 | cuda10.1 | cuda10.2 | cuda11.0 |
|:--|:--|:--|:--|:--|:--|
| 2.3.5  | gcc/4.8.5 | -   | -   | Yes | Yes |

!!! note
    計算ノード(A)では、現在 MVAPICH2-GDR を提供していません。

!!! note
    PGI 対応の MVAPICH2-GDR が必要な場合、ユーザーサポートまでご連絡ください。

## Intel MPI

| intel-mpi/ | Compute Node (V) | Compute Node (A) |
|:--|:--|:--|
| 2019.9 | Yes | Yes |
