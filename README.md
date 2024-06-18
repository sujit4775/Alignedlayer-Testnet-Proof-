
# ALIGNEDLAYER PUBLIC PROOF TASK



## Deployment

STEP 1
```bash
sudo apt update -y
sudo apt upgrade -y
```
Install curl

```bash
sudo apt-get install curl -y
```
Download ALignedProof

```bash

curl -L https://raw.githubusercontent.com/yetanotherco/aligned_layer/main/batcher/aligned/install_aligned.sh | bash
```
```bash
source /root/.bashrc
```
Download an example SP1 proof file with it's ELF file
```bash

curl -L https://raw.githubusercontent.com/yetanotherco/aligned_layer/main/batcher/aligned/get_proof_test_files.sh | bash
```

Sending proof
```bash
rm -rf ~/aligned_verification_data/ &&
aligned submit \
--proving_system SP1 \
--proof ~/.aligned/test_files/sp1_fibonacci.proof \
--vm_program ~/.aligned/test_files/sp1_fibonacci-elf \
--aligned_verification_data_path ~/aligned_verification_data \
--conn wss://batcher.alignedlayer.com
```
Wait 2 or 3 min after that
use this code to get the log you will screenshot for your X post
```bash
aligned verify-proof-onchain \
--aligned-verification-data ~/aligned_verification_data/*.json \
--rpc https://ethereum-holesky-rpc.publicnode.com \
--chain holesky
```
