# ETH-Denver-2025-DEMO


This demo showcases the latest research and development achievements of the [BitVM project](https://bitvm.org/).


It presents the first real-world use case of BitVM: the complete protocol process [BitVM Bridge](https://bitvm.org/bitvm_bridge.pdf). 


This demo marks a significant milestone for the BitVM project as it moves toward the next critical stage: a code audit of the foundational library.


# Process Set


- peg-in
- peg-out-Happy path
- peg-out-Unhappy path


# Reproduce Demo


Developers can use the following stuff to reproduce the processes in the local environment.


[Code base tag](https://github.com/BitVM/BitVM/releases/tag/v0.1.0-alpha)


[Instrudctions](https://github.com/BitVM/BitVM/blob/main/DEMO_INSTRUCTIONS.md)


# Public Signet Transactions


A public signet is set up for the BitVM development and testing. People can check the transactions in public signet explorer.


## Txn Graph


<style>
 .step-link {
   position: absolute;
   display: block;
   font-size: 12px;
   text-decoration: none;
 }
 .step-link:hover {
   text-decoration: underline;
 }
</style>
<div style="width: 100%; overflow-x: auto">
<div style="width: 951px; height: 458px; position: relative">
 <a
   target="_blank"
   rel="noreferrer"
   class="step-link"
   href="https://mempool.bitvmnet.org/tx/4dd5d195073af820875b5f19dc2ab30862798af2ea63fc37aecbe1051f1e8688"
   style="left: 150px; top: 75px"
   >Peg in deposit</a
 >
 <a
   target="_blank"
   rel="noreferrer"
   class="step-link"
   href="https://mempool.bitvmnet.org/tx/e9663b684cb15f255ef0a77fdcc5ffebcfa0ba06dc32b4650b3fab8d91da518f"
   style="left: 375px; top: 75px"
   >Peg in confirm</a
 >
 <a
   target="_blank"
   rel="noreferrer"
   class="step-link"
href="https://mempool.bitvmnet.org/tx/095c21cc45331da7fdb45f8f56e184c4d983cf86f539fd32ee39cc44543e71bd"    style="left: 750px; top: 200px; width: 50px; text-align: center"
   >Peg out (front)</a
 >
 <a
   target="_blank"
   rel="noreferrer"
   class="step-link"
href="https://mempool.bitvmnet.org/tx/1c74c2819717b3af854c2ab50b58001186e40f384fb8c1bd01791fce64cc7353"        style="left: 490px; top: 120px"
   >Peg out confirm</a
 >
 <a
   target="_blank"
   rel="noreferrer"
   class="step-link"
href="https://mempool.bitvmnet.org/tx/8d96aab47ef67279141ae0eeccf1b588ab9ad1d75fba1a6dd46a70845499006e"      style="left: 490px; top: 155px"
   >Kickoff1</a
 >
 <a
   target="_blank"
   rel="noreferrer"
   class="step-link"
   href="#"
   style="left: 150px; top: 376px"
   >Challenge</a
 >
 <a
   target="_blank"
   rel="noreferrer"
   class="step-link"
href="https://mempool.bitvmnet.org/tx/3c8d81f37e28f64b34a76e41b58788c94e1a7e7a0761c2d5a235aa956908243a"          style="left: 490px; top: 190px"
   >Kickoff2</a
 >
 <a
   target="_blank"
   rel="noreferrer"
   class="step-link"
href="https://mempool.bitvmnet.org/tx/8d386719cc3bc461e07c261a14419fd87b8e56374283b79e357b05b9fb3fd45c"     style="left: 490px; top: 222px"
   >Assert initial</a
 >
 <a
   target="_blank"
   rel="noreferrer"
   class="step-link"
href="https://mempool.bitvmnet.org/tx/bb29da2a87879faf46c22fbb19a3961b226c4a6075bad5226a6802472fbb0871"      style="left: 490px; top: 254px"
   >Assert commit1</a
 >
 <a
   target="_blank"
   rel="noreferrer"
   class="step-link"
href="https://mempool.bitvmnet.org/tx/93e951de5ce6335f588f344ff58d54e1d813fcecc192a186bf7e19d712556680"        style="left: 490px; top: 288px"
   >Assert commit2</a
 >
 <a
   target="_blank"
   rel="noreferrer"
   class="step-link"
href="https://mempool.bitvmnet.org/tx/e7da86777532342521f80bbf2bfc477ebbab289866b6c2842673a006ec34512a"      style="left: 490px; top: 323px"
   >Assert final</a
 >
 <a
   target="_blank"
   rel="noreferrer"
   class="step-link"
href="https://mempool.bitvmnet.org/tx/ee29855315760b5b839ad20c9ce19a1e235c54afc2431b2a527b97458c0ab8e5"     style="left: 360px; top: 378px"
   >Disprove</a
 >
 <img src="./graph.png" alt="Txn Graph">
</div>
</div>


## Txn List
Peg in: [https://mempool.bitvmnet.org/tx/4dd5d195073af820875b5f19dc2ab30862798af2ea63fc37aecbe1051f1e8688](https://mempool.bitvmnet.org/tx/4dd5d195073af820875b5f19dc2ab30862798af2ea63fc37aecbe1051f1e8688){:target="_blank"}


Peg in confirm: [https://mempool.bitvmnet.org/tx/e9663b684cb15f255ef0a77fdcc5ffebcfa0ba06dc32b4650b3fab8d91da518f](https://mempool.bitvmnet.org/tx/e9663b684cb15f255ef0a77fdcc5ffebcfa0ba06dc32b4650b3fab8d91da518f){:target="_blank"}


Peg out: [https://mempool.bitvmnet.org/tx/095c21cc45331da7fdb45f8f56e184c4d983cf86f539fd32ee39cc44543e71bd](https://mempool.bitvmnet.org/tx/095c21cc45331da7fdb45f8f56e184c4d983cf86f539fd32ee39cc44543e71bd){:target="_blank"}


Peg out confirm: [https://mempool.bitvmnet.org/tx/1c74c2819717b3af854c2ab50b58001186e40f384fb8c1bd01791fce64cc7353](https://mempool.bitvmnet.org/tx/1c74c2819717b3af854c2ab50b58001186e40f384fb8c1bd01791fce64cc7353){:target="_blank"}


Kickoff 1: [https://mempool.bitvmnet.org/tx/8d96aab47ef67279141ae0eeccf1b588ab9ad1d75fba1a6dd46a70845499006e](https://mempool.bitvmnet.org/tx/8d96aab47ef67279141ae0eeccf1b588ab9ad1d75fba1a6dd46a70845499006e){:target="_blank"}


Kickoff 2: [https://mempool.bitvmnet.org/tx/3c8d81f37e28f64b34a76e41b58788c94e1a7e7a0761c2d5a235aa956908243a](https://mempool.bitvmnet.org/tx/3c8d81f37e28f64b34a76e41b58788c94e1a7e7a0761c2d5a235aa956908243a){:target="_blank"}


Assert initial: [https://mempool.bitvmnet.org/tx/8d386719cc3bc461e07c261a14419fd87b8e56374283b79e357b05b9fb3fd45c](https://mempool.bitvmnet.org/tx/8d386719cc3bc461e07c261a14419fd87b8e56374283b79e357b05b9fb3fd45c){:target="_blank"}


Assert Commit 1: [https://mempool.bitvmnet.org/tx/bb29da2a87879faf46c22fbb19a3961b226c4a6075bad5226a6802472fbb0871](https://mempool.bitvmnet.org/tx/bb29da2a87879faf46c22fbb19a3961b226c4a6075bad5226a6802472fbb0871){:target="_blank"}


Assert Commit 2: [https://mempool.bitvmnet.org/tx/93e951de5ce6335f588f344ff58d54e1d813fcecc192a186bf7e19d712556680](https://mempool.bitvmnet.org/tx/93e951de5ce6335f588f344ff58d54e1d813fcecc192a186bf7e19d712556680){:target="_blank"}


Assert Final: [https://mempool.bitvmnet.org/tx/e7da86777532342521f80bbf2bfc477ebbab289866b6c2842673a006ec34512a](https://mempool.bitvmnet.org/tx/e7da86777532342521f80bbf2bfc477ebbab289866b6c2842673a006ec34512a){:target="_blank"}


Disprove: [https://mempool.bitvmnet.org/tx/ee29855315760b5b839ad20c9ce19a1e235c54afc2431b2a527b97458c0ab8e5](https://mempool.bitvmnet.org/tx/ee29855315760b5b839ad20c9ce19a1e235c54afc2431b2a527b97458c0ab8e5){:target="_blank"}


# About
This page is maintained by [BitVM Alliance](https://bitvm.org/#about-bitvm-alliance)

