
# ALIGNEDLAYER PUBLIC PROOF TASK
![340573200-4ab13f14-e030-46e4-84c2-ba4e9e6e73c3-2](https://github.com/sujit4775/Alignedlayer-Testnet-Proof-/assets/141178071/e9d163df-d61e-4071-bef0-9b924ca23d2d)


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

![WhatsApp Image 2024-06-18 at 10 53 13 PM](https://github.com/sujit4775/Alignedlayer-Testnet-Proof-/assets/141178071/efffe5eb-7f5e-4009-b96f-86dda7f16904)

```bash

curl -L https://raw.githubusercontent.com/yetanotherco/aligned_layer/main/batcher/aligned/install_aligned.sh | bash
```
```bash
source /root/.bashrc
```
Download an example SP1 proof file with it's ELF file

![WhatsApp Image 2024-06-18 at 10 58 25 PM](https://github.com/sujit4775/Alignedlayer-Testnet-Proof-/assets/141178071/d4431380-88ff-4d88-840e-bcaeb2751a59)

```bash

curl -L https://raw.githubusercontent.com/yetanotherco/aligned_layer/main/batcher/aligned/get_proof_test_files.sh | bash
```

Sending proof
![WhatsApp Image 2024-06-18 at 11 02 37 PM](https://github.com/sujit4775/Alignedlayer-Testnet-Proof-/assets/141178071/3569d018-c2c0-48fd-80e2-f1898a92dfb7)

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
![WhatsApp Image 2024-06-18 at 11 05 22 PM](https://github.com/sujit4775/Alignedlayer-Testnet-Proof-/assets/141178071/4ad380ab-d7bb-4912-a96f-5de21a4a4a54)

```bash
aligned verify-proof-onchain \
--aligned-verification-data ~/aligned_verification_data/*.json \
--rpc https://ethereum-holesky-rpc.publicnode.com \
--chain holesky
```
