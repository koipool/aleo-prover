# 使用说明

KOIPool Prover 使用纯显卡计算，对CPU基本没有占用，目前仅支持Nvidia，驱动525以上版本。

ubuntu下，使用如下命令安装驱动：
sudo apt install nvidia-headless-525 nvidia-utils-525

***

## 生成新密钥：

./aleo-prover --new-address

样本输出如下：
Private key: APrivateKey1zkpEH6qSaAuMiUqX6J8t5DzgGiJCs3vUxK26P1ir6pHiRqz
   View key: AViewKey1hmLNCwdZjBno8iK3bzwypD28WXgf6aFoZfuwcdzoQwSf
    Address: aleo1hduu04zrt7lsdt2htyu7ps5cgj5nk8s4jx43awk35mj7cnwy359smsfg88

其中Address是账号地址，其它都是私钥，请妥善保管

***

## SOLO 模式：

./aleo-prover -u -a aleo1hduu04zrt7lsdt2htyu7ps5cgj5nk8s4jx43awk35mj7cnwy359smsfg88 -n $(hostname) -p aleo-asia1.koipool.com:3808

其中地址为最终上链的地址

***

## 矿池模式

./aleo-prover -a aleo1hduu04zrt7lsdt2htyu7ps5cgj5nk8s4jx43awk35mj7cnwy359smsfg88 -n $(hostname) -p aleo-asia1.koipool.com:3808

其中地址为矿池分币地址。
注：当前为测试网络，转账交易还未上线，所以矿池模式待主网上线后按实际结算。

*** 

Usage:

```
KOIPool Aleo GPU Prover

Usage: aleo-prover [OPTIONS]

Options:
  -d, --debug                      Enable debug logging
  -a, --address <ADDRESS>          Prover address (aleo1...)
  -p, --pool <POOL>                Pool server address
  -o, --log <LOG>                  Output log to file
      --new-address                Generate a new address
  -n, --worker-name <WORKER_NAME>  
  -u, --use-individual-address     
  -g, --cuda <CUDA>                Indexes of GPUs to use (starts from 0)
                                   Specify multiple times to use multiple GPUs
                                   Example: -g 0 -g 1 -g 2
                                   Note: prover will use all available GPUs if no -g is specified
  -j, --cuda-jobs <CUDA_JOBS>      Parallel jobs per GPU, defaults to 2
                                   Example: -g 0 -g 1 -j 3
                                   more parallel jobs will cost more GPU memory [default: 2]
  -h, --help                       Print help information
  -V, --version                    Print version information
```
