### [ICSE'22] WindRanger: A Directed Greybox Fuzzer driven by Deviation Basic Block

[[paper]](https://drive.google.com/file/d/1VTlFoOE5uUzL7_b5OwGWCEcMDlNC_SBF/view) [[project]](https://sites.google.com/view/windranger-directed-fuzzing/home?authuser=0) [[talk]](https://www.youtube.com/watch?v=MUmaI4evzc4)
  
<details>
  <summary>Click to see the abstract!</summary>
Directed grey-box fuzzing (DGF) is a security testing technique that aims to steer the fuzzer towards predefined target sites in the program. To gain directness, DGF prioritizes the seeds whose execution traces are closer to the target sites. Therefore, evaluating the distance between the execution trace of a seed and the target sites (aka, the seed distance) is important for DGF. The first directed grey-box fuzzer, AFLGo, uses an approach of calculating the basic block level distances during static analysis and accumulating the distances of the executed basic blocks to compute the seed distance. <font color='red'>Following AFLGo, most of the existing state-of-the-art DGF techniques use all the basic blocks on the execution trace and only the control flow information for seed distance calculation.</font> However, <font color='red'>not every basic block is equally important and there are certain basic blocks where the execution trace starts to deviate from the target sites</font> (aka, deviation basic blocks).

In this paper, we propose a technique called WindRanger which <font color='red'>leverages deviation basic blocks to facilitate DGF.</font> To identify the deviation basic blocks, WindRanger applies both static reachability analysis and dynamic filtering. To conduct directed fuzzing, WindRanger uses the deviation basic blocks and their related data flow information for seed distance calculation, mutation, seed prioritization as well as explore-exploit scheduling. We evaluated WindRanger on 3 datasets consisting of 29 programs. The experiment results show that WindRanger outperforms AFLGo, AFL, and Fairfuzz by reaching the target sites 21%, 34%, and 37% faster and detecting the target crashes 44%, 66%, and 77% faster respectively. Moreover, we found a 0-day vulnerability with a CVE ID assigned in ffmpeg (a popular multimedia library extensively fuzzed by OSS-fuzz) with WindRanger by supplying manually identified suspect locations as the target sites.
</details>

--------------------------------------------------------------------------------------------------------------------------

### [arxiv'22] Multiple Targets Directed Greybox Fuzzing
  
[[paper]](https://arxiv.org/pdf/2206.14977.pdf) [[project]](https://github.com/HongliangLiang/leofuzz)

<details>
  <summary>Click to see the abstract!</summary>
Directed greybox fuzzing (DGF) can quickly discover or reproduce bugs in programs by seeking to reach a program location or explore some locations in order. However, <font color='red'>due to their static stage division and coarse-grained energy scheduling, prior DGF tools perform poorly when facing multiple target locations (targets for short).</font> <br>In this paper, <font color='red'>we present multiple targets directed greybox fuzzing which aims to reach multiple programs locations in a fuzzing campaign.</font> Specifically, we propose a novel strategy to adaptively coordinate exploration and exploitation stages, and a novel energy scheduling strategy by considering more relations between seeds and target locations. We implement our approaches in a tool called LeoFuzz and evaluate it on crash reproduction, true positives verification, and vulnerability exposure in real-world programs. Experimental results show that LeoFuzz outperforms six state-of-the-art fuzzers, i.e., QYSM, AFLGo, Lolly, Berry, Beacon and WindRanger in terms of effectiveness and efficiency. Moreover, LeoFuzz has detected 23 new vulnerabilities in real-world programs, and 11 of them have been assigned CVE IDs.
</details>

--------------------------------------------------------------------------------------------------------------------------

### [S&P'23] SELECTFUZZ: Efficient Directed Fuzzing with Selective Path Exploration

[[paper]](https://csdl-downloads.ieeecomputer.org/proceedings/sp/2023/9336/00/933600b050.pdf?Expires=1672859666&Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9jc2RsLWRvd25sb2Fkcy5pZWVlY29tcHV0ZXIub3JnL3Byb2NlZWRpbmdzL3NwLzIwMjMvOTMzNi8wMC85MzM2MDBiMDUwLnBkZiIsIkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTY3Mjg1OTY2Nn19fV19&Signature=IHxAaMfG4NH8KIS~~p~jcceRLTaa2g~ycPozrqmd32BjBgMJubIjijrHoqnFJajhk0yEQgQXsf8z4PzsWXSV4XpI1m6AbpVYDib-YC6nr3DHheezNDdWFkwv8vI2jcMuxBsRU7mgZ7hT89YtD1OM1USnlaEXmzfPVJ~o0AJKD44isdnfnIPNLo2u~pIme04mFmR-xP~k8TMv-44jQ6O~ktmABwsR2TEY9dPL7BZI8BgOMqVXFciFiAMN5nfbT8qcWP0zDajFXl4Dv1cGL0axOFx-fnxARaNeTIXFGpad8aNV0uFcWKAGvZSKRnJv9WFiK5Ya57MjvUT217i4~1ZYnQ__&Key-Pair-Id=K12PMWTCQBDMDT) [[project]](https://github.com/cuhk-seclab/SelectFuzz)

<details>
  <summary>Click to see the abstract!</summary>
Directed grey-box fuzzers specialize in testing specific target code. They have been applied to many security applications such as reproducing known crashes and detecting vulnerabilities caused by incomplete patches. However, existing directed fuzzers favor the inputs discovering new code regardless whether the newly uncovered code is relevant to the target code or not. As a result, the fuzzers would extensively explore irrelevant code and
suffer from low efficiency. <br>In this paper, we distinguish relevant code in the target program from the irrelevant one that does not help trigger the vulnerabilities in target code. We present SELECTFUZZ, <font color='red'>a new directed fuzzer that selectively explores relevant program paths for</font> efficient crash reproduction and vulnerability detection. It identifies two types of relevant code—path-divergent code and data-dependent code, that respectively captures the controland data-dependency with the target code. <font color='red'>It then selectively instruments and explores only the relevant code blocks.</font> We also propose a new distance metric that accurately measures the reaching probability of different program paths and inputs.<br> We evaluated SELECTFUZZ with real-world vulnerabilities in sets of diverse programs. SELECTFUZZ significantly outperformed a baseline directed fuzzer by up to 46.31×, and performed the best in the Google Fuzzer Test Suite. Our experiments also demonstrated that SELECTFUZZ and the existing techniques such as path pruning are complementary. Finally, with SELECTFUZZ, we detected 14 previously unknown vulnerabilities—including 6 new CVE IDs—in well tested real-world software. Our report has led to the fix of 11 vulnerabilities.
</details>

--------------------------------------------------------------------------------------------------------------------------

### [Usenix'23] FishFuzz: Catch Deeper Bugs by Throwing Larger Nets

[[paper]](https://nebelwelt.net/files/23SEC5.pdf) [[project]](https://github.com/HexHive/FishFuzz) [[artifact]](https://zenodo.org/record/6405418) 
  
<details>
  <summary>Click to see the abstract!</summary>
Fuzzers effectively explore programs to discover bugs. Greybox fuzzers mutate seed inputs and observe their execution. Whenever a seed reaches new behavior (e.g., new code or higher execution frequency), it is stored for further mutation. Greybox fuzzers directly measure exploration and, by repeating execution of the same targets with large amounts of mutated seeds, passively exploit any lingering bugs. <font color='red'>Directed greybox fuzzers (DGFs) narrow the search to a few code locations but so far generalize distance to all targets into a single score and do not prioritize targets dynamically.</font>

FISHFUZZ introduces an input prioritization strategy that builds on three concepts: (i) a novel multi-distance metric whose precision is independent of the number of targets, (ii) <font color='red'>a dynamic target ranking to automatically discard exhausted targets</font>, and (iii) a smart queue culling algorithm, based on hyperparameters, that alternates between exploration and exploitation. <font color='red'>FISHFUZZ enables fuzzers to seamlessly scale among thousands of targets</font> and prioritize seeds toward interesting locations, thus achieving more comprehensive program testing. To demonstrate generality, we implement FISHFUZZ over two well-established greybox fuzzers (AFL and AFL++). We evaluate FISHFUZZ by leveraging all sanitizer labels as targets. In comparison to modern DGFs and state-of-the-art coverage guided fuzzers, FISHFUZZ reaches higher coverage compared to the direct competitors, finds up to 2.8x more
bugs compared with the baseline and reproduces 68.3% existing bugs faster. FISHFUZZ also discovers 56 new bugs (38 CVEs) in 47 programs.
</details>

--------------------------------------------------------------------------------------------------------------------------

### [Usenix'23] DAFL: Directed Grey-box Fuzzing Guided by Data Dependency

[[paper]](https://prosys.kaist.ac.kr/publications/sec23.pdf) [[project]](https://github.com/prosyslab/DAFL-artifact) [[artifact]](https://zenodo.org/record/8031029) [[slides]](https://www.usenix.org/system/files/sec23_slides_kim-tae.pdf)
  
<details>
  <summary>Click to see the abstract!</summary>
<font color='red'>Despite growing research interest, existing directed greybox fuzzers do not scale well with program complexity.</font> In this paper, we identify two major scalability challenges for
current directed grey-box fuzzing. Particularly, we find that traditional coverage feedback does not always provide meaningful guidance for reaching the target program point(s), and
<font color='red'>the existing seed distance mechanism does not operate well with programs with complex control structures.</font> To address these problems, we present a novel fuzzer, named DAFL. <font color='red'>DAFL selects code parts that are relevant to the target location and obtains coverage feedback only from those parts.</font> Furthermore, it computes precise seed distances considering the data-flow semantics of program executions. The results are promising. Out of 41 real-world bugs, DAFL was able to find 4, 6, 9, and 5 more bugs within the given time, compared to AFL, AFLGo, WindRanger, and Beacon, respectively. Furthermore, among the cases where all fuzzers produced a median TTE, DAFL was at least 4.99 times faster on average compared to 3 state-of-the-art directed fuzzers including AFLGo, WindRanger, and Beacon.
</details>

--------------------------------------------------------------------------------------------------------------------------

### [S&P'24] Titan : Efficient Multi-target Directed Greybox Fuzzing

[[paper]](https://5hadowblad3.github.io/files/Oakland24-Titan.pdf) [[project]](https://github.com/5hadowblad3/Titan)

<details>
  <summary>Click to see the abstract!</summary>
<font color='red'>Modern directed fuzzing often faces scalability issues when analyzing multiple targets in a program simultaneously</font>. We observe that the root cause is that directed fuzzers are unaware of the correlations among the targets, thereby could degenerate into a target-undirected method. As a result, directed fuzzing suffers severely from efficiency when reproducing multiple targets. <br> This paper presents Titan, which enables fuzzers to <font color='red'>distinguish correlations among various targets in the program</font> and, thus, <font color='red'>optimizes the input generation to reproduce multiple targets effectively</font>. Leveraging these correlations, Titan differentiates seeds’ potential of reaching each target for the scheduling and identifies bytes that can be changed simultaneously for the mutation. We compare our approach to eight state-of-the-art (directed) fuzzers. The evaluation demonstrates that Titan outperforms existing approaches by efficiently detecting multiple targets, achieving a 21.4x speedup and requiring 95.0% fewer number of executions. In addition, Titan detects ten incomplete fixes, which cannot be detected by other directed fuzzers, in the latest versions of the benchmark programs with two CVE IDs assigned.
</details>

--------------------------------------------------------------------------------------------------------------------------
