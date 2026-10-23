# Supplementary Table S1 — Corpus classification

This file accompanies the survey *Unmanned Aerial Systems for Crop and Livestock Farming: A System-Oriented Survey of Sensing, Intelligence, Connectivity, and Autonomy*. It lists every paper in the corpus with its codes in the survey's taxonomy, so that every count reported in the paper can be checked. The same data are in `S1_classification.csv`.

## 1. How the corpus was built

- **Search.** Google Scholar, July–August 2026, 166 keyword queries in 18 groups, run in two stages (full list in Supplementary Table S2, `S2_queries.md`). The first stage paired "UAV" with a crop or livestock application, a sensing modality, onboard intelligence, communications, planning, or an operational constraint (energy, payload). Because it returned few livestock records, the second stage added livestock-specific queries on detection and counting, behavior, welfare and health, and pasture and grazing, together with livestock variants of the sensing, vision, multi-UAV, and field-validation queries. Existing surveys were also queried and snowballed.
- **Selection.** Peer-reviewed journal and conference papers from 2019 onward, in English, issued by a recognized publisher, in which a UAS is the platform or the explicit design target and the application is crop production, livestock production, or pasture (grazed vegetation). Preprints, theses, and technical reports were excluded. Among eligible records, established venues in agricultural engineering, remote sensing, animal science, robotics, and communications were favored; this judgment was qualitative, and the corpus spans 129 venues.
- **Coverage check.** A targeted search on autonomous, onboard-perception, and multi-UAV livestock operation added one study.
- **Result.** 271 papers: 240 primary studies (including 7 dataset and 4 position papers), 28 surveys, and 3 background papers.

The corpus is a purposive sample. Counts describe the corpus, not the whole field.

## 2. How each paper was coded

One author read every paper in full and wrote a standardized review (summary, relevance, strengths, weaknesses, and a cross-check of the paper's claims against its own evidence). A second author classified the papers from these reviews. At least two authors agreed on the final loop-level assignments, and every study at L2–L4 was checked a second time against its review. A paper is classified by what it **implements and evaluates**, not by what it proposes or motivates. Surveys and background papers are not classified and have `NA` in the taxonomy columns.

### Loop coverage (L) — primary dimension

A *decision* is an instruction on what to do, such as a spray map, an irrigation quota, or an alert; an *action* is its physical execution by the UAS. Where farm staff rather than the aircraft execute a decision, as in much of livestock care, the study is coded L2: the level records what the UAS does, not whether the study is complete.

| Code | Name | A study is coded here when… |
|---|---|---|
| L0 | Enabler | it contributes a platform, network, planner, controller, energy, or data component, and no agricultural target is perceived or treated in its evaluation |
| L1p | Perception product | UAV data are turned into an estimate, map, or detection of an agricultural target, and no decision is produced |
| L1a | Action without target perception | the UAV sprays, herds, or hazes with preset settings, or with settings driven by a prescription or telemetry, without perceiving the target |
| L2 | Decision not executed | perception yields a prescription, quota, mission, or alert that is not executed in the study |
| L3 | Decoupled loop | perception, decision, and action are all executed, but in separate missions or operations (e.g., map then spray) |
| L4 | In-mission loop | perception of the agricultural target changes the UAV's flight or actuation during the same mission |

Boundary rules:
1. A loop closed on telemetry, wind, or position against a prescription map is L1a, not L4, because the target is not perceived.
2. A prescription computed offline and looked up in flight is L3, even if flow control runs onboard.
3. A re-plan confirmed by an operator is L4 when the re-plan itself is computed from perception.
4. Maturity is coded separately: a simulated controller and a field-tested system can share the same L level.

### Complementary dimensions

- **Function (F):** F1 crop and soil characterization; F2 crop object detection and counting; F3 input application and its effects; F4 livestock and pasture observation; F5 animal response and guidance; F6 farm data infrastructure; F7 flight and mission enablers. F6 and F7 correspond to L0.
- **Domain (D):** crop; livestock; pasture (grazed vegetation serving livestock decisions); wildlife-analogue (wildlife studies whose method transfers to livestock); cross-domain.
- **Maturity (M):** M0 concept; M1 simulation; M2 laboratory or bench; M3 controlled field; M4 farm trial (one campaign on a commercial farm); M5 operational (repeated, routine-like use or several farms).
- **Measured resources (R):** which of computation (`compute`), communication (`comms`), and energy are measured on hardware, as opposed to simulated or asserted; `none` if none is measured.
- **Sensing (S):** sensing modalities as reported (descriptive, not a classification axis).
- **Artifacts:** `released` (data and/or code available), `on request`, or `none` (no availability stated).

`AMBIGUOUS` marks a value that could not be determined from the review (one study on L, one on M).

## 3. Summary counts (240 primary studies)

| Loop coverage | n |
|---|---|
| AMBIGUOUS | 1 |
| L0 | 61 |
| L1a | 29 |
| L1p | 125 |
| L2 | 7 |
| L3 | 4 |
| L4 | 13 |

| Function | n |
|---|---|
| F1 | 63 |
| F2 | 33 |
| F3 | 35 |
| F4 | 38 |
| F5 | 11 |
| F6 | 21 |
| F7 | 39 |

| Domain | n |
|---|---|
| crop | 161 |
| cross-domain | 18 |
| livestock | 51 |
| pasture | 6 |
| wildlife-analogue | 4 |

| Maturity | n |
|---|---|
| AMBIGUOUS | 1 |
| M0 | 6 |
| M1 | 45 |
| M2 | 15 |
| M3 | 69 |
| M4 | 89 |
| M5 | 15 |

| Measured resources | n |
|---|---|
| comms | 7 |
| comms+energy | 2 |
| compute | 25 |
| compute+comms | 2 |
| compute+energy | 4 |
| energy | 9 |
| none | 191 |

| Artifacts | n |
|---|---|
| none | 202 |
| on request | 11 |
| released | 27 |

## 4. Classification table

`#` refers to the bibliography in Section 5. Primary studies come first, then surveys and background papers.

| # | Key | Year | Type | D | F | L | M | R | Artifacts |
|---|---|---|---|---|---|---|---|---|---|
| 1 | Afsar2025Mangispectra | 2025 | primary | crop | F1 | L1p | M5 | none | none |
| 2 | Ahmad2025Iout | 2025 | primary | cross-domain | F6 | L0 | M1 | none | none |
| 3 | Ahmed2022Lora | 2022 | primary | crop | F6 | L0 | M2 | none | none |
| 4 | Akbari2024Aware | 2024 | primary | cross-domain | F6 | L0 | M1 | none | none |
| 5 | Alanezi2022Livestock | 2022 | primary | livestock | F7 | L0 | M1 | none | none |
| 6 | Alanezi2022Ruber | 2022 | primary | livestock | F6 | L0 | M1 | none | none |
| 7 | Alanezi2022Uber | 2022 | primary | livestock | F6 | L0 | M1 | none | none |
| 8 | Almstedt2025Beyond | 2025 | primary | crop | F2 | L1p | M4 | none | none |
| 9 | Almstedt2025Comprehensive | 2025 | primary | crop | F2 | L1p | M4 | comms | none |
| 10 | AlNajadi2025Effectiveness | 2025 | primary | crop | F1 | L1p | M3 | none | none |
| 11 | Amarasingam2025Mapping | 2025 | primary | crop | F2 | L1p | M4 | none | none |
| 12 | anon2023Spray | 2023 | primary | crop | F3 | L1a | M3 | none | none |
| 13 | Anzai2022Preliminary | 2022 | primary | livestock | F5 | L1a | M4 | none | none |
| 14 | Anzai2023Effects | 2023 | primary | livestock | F5 | L1a | M4 | none | none |
| 15 | Apostolidis2022Cooperative | 2022 | primary | crop | F7 | L0 | M4 | none | none |
| 16 | ArizaSents2023Object | 2023 | dataset | crop | F2 | L1p | M4 | none | released |
| 17 | Baek2026Reduction | 2026 | primary | crop | F3 | L1a | M4 | none | none |
| 18 | Bakas2025Citrus | 2025 | primary | crop | F2 | L1p | M4 | compute | none |
| 19 | Bastos2024Drones | 2024 | primary | livestock | F4 | L1p | M5 | none | none |
| 20 | Benalaya2022Search | 2022 | primary | livestock | F7 | L0 | M1 | none | none |
| 21 | Benalaya2026Linear | 2026 | primary | livestock | F7 | L0 | M1 | none | none |
| 22 | Bertalan2022Multispectral | 2022 | primary | crop | F1 | L1p | M3 | none | none |
| 23 | BettiSorbelli2023Yolo | 2023 | dataset | crop | F2 | L1p | M4 | none | none |
| 24 | Bian2022Prediction | 2022 | primary | crop | F1 | L1p | M3 | none | none |
| 25 | Bilal2025Consumer | 2025 | primary | crop | F7 | L0 | M1 | none | none |
| 26 | Biscamps2025Laboratory | 2025 | primary | crop | F1 | L1p | M4 | none | none |
| 27 | Blekanov2023Monitoring | 2023 | primary | crop | F1 | L2 | M3 | none | none |
| 28 | Bokani2025Lstm | 2025 | primary | livestock | F7 | L0 | M1 | none | none |
| 29 | Boubin2022Adaptive | 2022 | primary | crop | F2 | AMBIGUOUS | M4 | energy | none |
| 30 | Bouchekara2022Sift | 2022 | primary | livestock | F4 | L1p | M2 | compute | none |
| 31 | Bouchekara2024Tuber | 2024 | primary | livestock | F6 | L0 | M1 | none | none |
| 32 | BrbuloBarrios2024Monitoring | 2024 | primary | livestock | F4 | L1p | M4 | none | released |
| 33 | Bukowiecki2024Canopy | 2024 | primary | crop | F1 | L1p | M3 | none | on request |
| 34 | BurchardLevine2024Evaluating | 2024 | primary | crop | F1 | L1p | M3 | none | none |
| 35 | BurchardLevine2025Evaluating | 2025 | primary | crop | F1 | L1p | M3 | none | released |
| 36 | Calderone2025Monitoring | 2025 | primary | livestock | F4 | L1p | M3 | none | none |
| 37 | Cantrk2023Individual | 2023 | primary | crop | F2 | L1p | M3 | none | none |
| 38 | Carracelas2024Assessing | 2024 | primary | crop | F1 | L1p | M3 | none | on request |
| 39 | Castro2023Adaptive | 2023 | primary | crop | F7 | L0 | M1 | none | released |
| 40 | CatalaRoman2024Autonomous | 2024 | primary | crop | F3 | L2 | M4 | compute | none |
| 41 | Chen2022Preliminary | 2022 | primary | crop | F3 | L1a | M3 | none | none |
| 42 | Chen2024Learning | 2024 | primary | crop | F7 | L0 | M1 | none | released |
| 43 | Chen2025Dasnet | 2025 | dataset | livestock | F4 | L1p | M4 | compute | released |
| 44 | Chen2025Efficient | 2025 | primary | livestock | F4 | L1p | M4 | none | none |
| 45 | Chen2025Field | 2025 | primary | crop | F3 | L3 | M4 | none | none |
| 46 | Chen2025Pesticide | 2025 | primary | crop | F3 | L1a | M4 | none | none |
| 47 | Chen2025Reinforcement | 2025 | primary | cross-domain | F6 | L0 | M1 | none | none |
| 48 | Cheng2023Evaluation | 2023 | primary | crop | F1 | L1p | M3 | none | none |
| 49 | Chittoor2023Assessment | 2023 | primary | cross-domain | F6 | L0 | M2 | energy | none |
| 50 | Chou2025Energy | 2025 | primary | crop | F7 | L0 | M1 | none | none |
| 51 | Cui2024Exploring | 2024 | primary | crop | F2 | L1p | M2 | compute | none |
| 52 | Dadallage2024Mask | 2024 | primary | livestock | F4 | L1p | M4 | none | none |
| 53 | deLimaWeber2023Counting | 2023 | primary | livestock | F4 | L1p | M4 | none | none |
| 54 | Divazi2025Experimental | 2025 | primary | crop | F3 | L1a | M2 | none | none |
| 55 | Duan2024Estimation | 2024 | primary | crop | F1 | L3 | M3 | none | none |
| 56 | Duttenhefner2024Spraying | 2024 | primary | crop | F5 | L1a | M5 | none | none |
| 57 | Ergunsah2023Energy | 2023 | primary | wildlife-analogue | F6 | L0 | M1 | none | none |
| 58 | Eun2024Comparison | 2024 | primary | crop | F3 | L1a | M4 | none | none |
| 59 | Fahad2025Innovative | 2025 | primary | cross-domain | F7 | L0 | M1 | none | released |
| 60 | Fendji2020Cost | 2020 | primary | cross-domain | F7 | L0 | M1 | none | none |
| 61 | Fu2024Research | 2024 | primary | crop | F7 | L0 | M1 | none | none |
| 62 | Ganeva2022Phenotypic | 2022 | primary | crop | F1 | L1p | M3 | none | none |
| 63 | Gao2024Analysis | 2024 | primary | livestock | F4 | L1p | M4 | none | on request |
| 64 | Giannetti2024First | 2024 | primary | crop | F2 | L1p | M4 | none | none |
| 65 | Gne2025Optimizing | 2025 | primary | crop | F3 | L1a | M4 | none | none |
| 66 | Guo2024Improving | 2024 | primary | crop | F1 | L1p | M3 | none | none |
| 67 | Guo2024Intelligent | 2024 | primary | crop | F3 | L3 | M4 | compute | none |
| 68 | Guo2025Cmtnet | 2025 | primary | crop | F1 | L1p | M4 | none | released |
| 69 | Hegde2022Multi | 2022 | primary | crop | F7 | L0 | M1 | none | none |
| 70 | Hijikata2026Hierarchical | 2026 | primary | crop | F7 | L0 | M1 | compute | none |
| 71 | Hobart2025Fruit | 2025 | primary | crop | F2 | L1p | M4 | none | none |
| 72 | Holtorf2023Wireless | 2023 | primary | crop | F6 | L0 | M4 | comms+energy | none |
| 73 | Htt2023Lidar | 2023 | primary | crop | F1 | L1p | M3 | none | none |
| 74 | Htt2024Lidar | 2024 | primary | pasture | F4 | L2 | M4 | none | none |
| 75 | Hua2021Fault | 2021 | primary | crop | F7 | L0 | M2 | none | none |
| 76 | Hua2024Fractional | 2024 | primary | crop | F7 | L0 | M2 | none | none |
| 77 | Huang2023Autonomous | 2023 | primary | crop | F7 | L0 | M3 | none | none |
| 78 | Huang2026Yolo | 2026 | primary | livestock | F4 | L1p | M4 | compute | released |
| 79 | Hussain2026Advancing | 2026 | primary | crop | F1 | L1p | M3 | none | none |
| 80 | Hwerbi2023Veterinary | 2023 | primary | livestock | F6 | L0 | M1 | comms | none |
| 81 | Ijaz2024Robust | 2024 | primary | crop | F7 | L0 | M1 | compute | none |
| 82 | Impollonia2022Remote | 2022 | primary | crop | F1 | L1p | M3 | none | none |
| 83 | Islam2025Towards | 2025 | primary | crop | F2 | L1p | M4 | compute | none |
| 84 | Jasim2023Evaluation | 2023 | primary | cross-domain | F7 | L0 | M0 | none | none |
| 85 | Jawad2019Wireless | 2019 | primary | cross-domain | F6 | L0 | M2 | energy | none |
| 86 | Jeon2025Study | 2025 | primary | crop | F3 | L1a | M3 | none | none |
| 87 | Ji2022Estimation | 2022 | primary | crop | F1 | L1p | M3 | none | none |
| 88 | Ji2023Assisted | 2023 | primary | livestock | F4 | L1p | M5 | none | none |
| 89 | Jiang2025Wind | 2025 | primary | crop | F7 | L0 | M1 | none | none |
| 90 | Jinyu2025Robotic | 2025 | position | livestock | F5 | L4 | M1 | none | none |
| 91 | Kaushal2024Enhancing | 2024 | primary | crop | F1 | L1p | M3 | none | none |
| 92 | Khan2021Real | 2021 | primary | crop | F3 | L1p | M4 | compute | none |
| 93 | Khose2024Spatial | 2024 | primary | crop | F1 | L1p | M3 | none | on request |
| 94 | Killeen2024Corn | 2024 | primary | crop | F1 | L1p | M4 | none | none |
| 95 | Kim2020Battery | 2020 | primary | cross-domain | F7 | L0 | M2 | energy | none |
| 96 | Kim2023Monitoring | 2023 | primary | crop | F3 | L1a | M5 | none | none |
| 97 | King2023Biologically | 2023 | position | livestock | F5 | L4 | M0 | none | none |
| 98 | Kizielewicz2025Multi | 2025 | primary | cross-domain | F7 | L0 | M0 | none | none |
| 99 | Kodors2024Autonomous | 2024 | primary | crop | F2 | L1p | M4 | compute | released |
| 100 | Koshelev2023Drone | 2023 | primary | crop | F2 | L1p | M4 | compute+energy | none |
| 101 | Krestenitis2024Overcome | 2024 | primary | crop | F2 | L4 | M1 | none | released |
| 102 | Kuang2026Intelligent | 2026 | primary | crop | F1 | L1p | M3 | none | none |
| 103 | Kumar2024Design | 2024 | primary | crop | F2 | L4 | M2 | compute | released |
| 104 | Kutyrev2025Sustainable | 2025 | primary | crop | F2 | L1p | M4 | none | none |
| 105 | Lacerda2022Thermal | 2022 | primary | crop | F1 | L1p | M3 | none | none |
| 106 | Lambertini2022Technical | 2022 | primary | crop | F7 | L0 | M4 | none | none |
| 107 | Lan2024Risk | 2024 | primary | crop | F3 | L1a | M4 | none | none |
| 108 | LaraMolina2025Optimization | 2025 | primary | crop | F3 | L2 | M1 | none | none |
| 109 | LarochePinel2024Assessing | 2024 | primary | crop | F1 | L1p | M3 | none | none |
| 110 | Lee2022Development | 2022 | primary | crop | F7 | L0 | M3 | comms | none |
| 111 | Li2022Effect | 2022 | primary | crop | F3 | L1a | M4 | none | none |
| 112 | Li2022Rapid | 2022 | primary | crop | F7 | L0 | M3 | energy | none |
| 113 | Li2022Robotic | 2022 | primary | livestock | F5 | L4 | M1 | none | none |
| 114 | Li2022Yield | 2022 | primary | crop | F2 | L1p | M4 | none | none |
| 115 | Li2023Coverage | 2023 | primary | crop | F7 | L0 | M4 | none | none |
| 116 | Li2023Imagery | 2023 | primary | crop | F1 | L1p | M3 | none | none |
| 117 | Li2023Longan | 2023 | primary | crop | F2 | L1p | M4 | none | none |
| 118 | Li2024Constrained | 2024 | primary | cross-domain | F6 | L0 | M1 | none | none |
| 119 | Li2025Influence | 2025 | primary | crop | F3 | L1a | M4 | none | none |
| 120 | Lin2022Quick | 2022 | primary | crop | F2 | L1p | M3 | compute | none |
| 121 | Lin2025Optimization | 2025 | primary | cross-domain | F7 | L0 | M2 | energy | none |
| 122 | Lipovac2022Correlation | 2022 | primary | crop | F1 | L1p | M3 | none | none |
| 123 | Lishchynskyi2024Trajectory | 2024 | primary | livestock | F4 | L1p | M4 | compute | none |
| 124 | Liu2024Immersive | 2024 | primary | crop | F7 | L0 | M4 | none | none |
| 125 | Liu2024Study | 2024 | primary | crop | F3 | L1a | M2 | none | none |
| 126 | Liu2025Lidar | 2025 | primary | crop | F3 | L3 | M3 | compute | none |
| 127 | Liu2025Multi | 2025 | primary | cross-domain | F6 | L0 | M1 | compute | none |
| 128 | Liu2025Remote | 2025 | primary | crop | F1 | L1p | M3 | none | none |
| 129 | Liu2026Quantifying | 2026 | primary | livestock | F4 | L1p | M5 | none | none |
| 130 | Los2023Estimating | 2023 | primary | livestock | F4 | L1p | M3 | none | none |
| 131 | Lpez2024Classification | 2024 | primary | crop | F1 | L1p | M4 | none | on request |
| 132 | Lukas2022Identify | 2022 | primary | crop | F1 | L1p | M3 | none | none |
| 133 | Luo2024 | 2024 | primary | livestock | F4 | L4 | M4 | none | none |
| 134 | Machidon2025Cost | 2025 | dataset | crop | F2 | L1p | M4 | compute+energy | released |
| 135 | Mansur2025Mapping | 2025 | primary | crop | F7 | L0 | M4 | none | none |
| 136 | Mayer2024Monitoring | 2024 | primary | wildlife-analogue | F5 | L1p | M4 | none | none |
| 137 | Mcher2022Detection | 2022 | primary | livestock | F4 | L1p | M4 | none | none |
| 138 | Meiyan2022Estimating | 2022 | primary | crop | F1 | L1p | M3 | none | none |
| 139 | Meng2022Spraying | 2022 | primary | crop | F3 | L1a | M4 | none | released |
| 140 | Menshchikov2021Real | 2021 | primary | crop | F2 | L1p | M2 | compute+energy | released |
| 141 | Meron2025Irrigation | 2025 | primary | crop | F1 | L1p | M5 | none | none |
| 142 | Mishra2023Internet | 2023 | position | livestock | F4 | L1p | M0 | none | none |
| 143 | Molins2026Applied | 2026 | primary | livestock | F5 | L1p | M3 | none | none |
| 144 | Moresi2025Monitoring | 2025 | primary | crop | F1 | L1p | M4 | none | none |
| 145 | Mukhamediev2023Coverage | 2023 | primary | cross-domain | F7 | L0 | M1 | none | released |
| 146 | Naidu2025Integrating | 2025 | position | crop | F7 | L0 | M0 | none | none |
| 147 | Nasir2026Vision | 2026 | primary | crop | F2 | L1p | M4 | none | none |
| 148 | Nazzari2025Modular | 2025 | primary | cross-domain | F7 | L0 | M4 | comms | released |
| 149 | Nguyen2023Efficient | 2023 | primary | crop | F6 | L0 | M1 | none | none |
| 150 | Nguyen2024Decentralized | 2024 | primary | livestock | F5 | L4 | M1 | none | none |
| 151 | Okada2024High | 2024 | primary | crop | F1 | L1p | M3 | none | on request |
| 152 | Orioli2026Integrating | 2026 | primary | livestock | F4 | L1p | M5 | none | none |
| 153 | Ortega2022Proposal | 2022 | primary | livestock | F6 | L0 | M4 | comms | released |
| 154 | Pakeman2025Assessing | 2025 | primary | pasture | F4 | L1p | M3 | none | none |
| 155 | Panjaitan2022Drone | 2022 | primary | crop | F3 | L1a | M4 | energy | none |
| 156 | Pdua2024Assessing | 2024 | primary | pasture | F4 | L1p | M4 | none | none |
| 157 | Pdua2024Detection | 2024 | primary | crop | F1 | L1p | M4 | none | none |
| 158 | Peng2025Research | 2025 | primary | crop | F2 | L1p | M4 | compute | none |
| 159 | Pierdicca2024Multi | 2024 | primary | crop | F2 | L4 | M1 | none | none |
| 160 | Qin2023Productivity | 2023 | primary | crop | F3 | L1a | M5 | none | none |
| 161 | Qin2026Multiple | 2026 | primary | crop | F7 | L0 | M1 | none | none |
| 162 | Qu2024Drone | 2024 | primary | crop | F1 | L1p | M3 | none | none |
| 163 | R2025Precision | 2025 | primary | cross-domain | F6 | L0 | M4 | comms+energy | none |
| 164 | Rai2024Agricultural | 2024 | primary | crop | F2 | L1p | M4 | compute+energy | none |
| 165 | Ramteke2025Optimizing | 2025 | primary | crop | F3 | L1a | M5 | none | none |
| 166 | Ranelovi2023High | 2023 | primary | crop | F1 | L1p | M3 | none | on request |
| 167 | Raptis2023Precision | 2023 | primary | crop | F2 | L4 | M4 | none | released |
| 168 | Rayner2024Distance | 2024 | primary | livestock | F4 | L1p | M4 | none | none |
| 169 | Rietz2023Drone | 2023 | primary | wildlife-analogue | F4 | L1p | M4 | none | none |
| 170 | Rocha2025Drones | 2025 | primary | livestock | F5 | L1p | M5 | none | none |
| 171 | Rodene2022High | 2022 | primary | crop | F1 | L1p | M3 | none | released |
| 172 | Sadiq2024High | 2024 | primary | livestock | F4 | L2 | M1 | none | none |
| 173 | Sadiq2025Wire | 2025 | primary | livestock | F6 | L0 | M1 | none | none |
| 174 | Safaeinejad2025Reducing | 2025 | primary | crop | F3 | L1a | M4 | energy | none |
| 175 | Sankararao2022Water | 2022 | primary | crop | F1 | L1p | M3 | none | none |
| 176 | Sankararao2023Machine | 2023 | primary | crop | F1 | L1p | M3 | none | none |
| 177 | Shafiee2023Evaluation | 2023 | primary | crop | F1 | L1p | M3 | none | on request |
| 178 | Shammi2024Application | 2024 | primary | crop | F1 | L1p | M3 | none | on request |
| 179 | Sharma2024Remote | 2024 | primary | crop | F1 | L1p | M3 | none | none |
| 180 | Shen2022Improving | 2022 | primary | crop | F1 | L1p | M3 | none | none |
| 181 | Shen2024High | 2024 | primary | crop | F1 | L1p | M3 | compute | none |
| 182 | Shen2024Improved | 2024 | primary | livestock | F4 | L1p | AMBIGUOUS | compute | none |
| 183 | Shi2022Research | 2022 | primary | wildlife-analogue | F5 | L4 | M1 | none | none |
| 184 | Shokati2024Random | 2024 | primary | crop | F1 | L1p | M3 | none | on request |
| 185 | Singh2024Smart | 2024 | primary | crop | F3 | L4 | M3 | compute | none |
| 186 | Sorbelli2022Drone | 2022 | primary | crop | F7 | L0 | M4 | none | none |
| 187 | Sorbelli2023Preliminary | 2023 | dataset | crop | F2 | L1p | M2 | none | none |
| 188 | Spizzirri2026Direct | 2026 | primary | livestock | F4 | L1p | M5 | none | none |
| 189 | Stache2023Adaptive | 2023 | primary | crop | F2 | L4 | M1 | none | none |
| 190 | Subeesh2024Imagery | 2024 | primary | crop | F2 | L1p | M4 | none | none |
| 191 | Sun2024Accurate | 2024 | primary | crop | F1 | L2 | M3 | none | none |
| 192 | T2024Fuzzy | 2024 | primary | cross-domain | F7 | L0 | M1 | none | none |
| 193 | Tian2024Mure | 2024 | primary | livestock | F6 | L0 | M1 | none | none |
| 194 | Tulu2025Agrisenai | 2025 | primary | crop | F1 | L1p | M3 | none | released |
| 195 | Turnip2024Design | 2024 | primary | crop | F3 | L1a | M3 | none | none |
| 196 | Umeda2022Cost | 2022 | primary | crop | F3 | L1a | M5 | none | none |
| 197 | Vaghalandari2025Performance | 2025 | primary | crop | F6 | L0 | M1 | comms | none |
| 198 | Vahidi2025Multi | 2025 | primary | crop | F1 | L1p | M4 | none | none |
| 199 | VallejosFernndez2026Monitoring | 2026 | primary | pasture | F4 | L1p | M5 | none | none |
| 200 | Vannini2023Harpia | 2023 | primary | crop | F7 | L0 | M1 | none | none |
| 201 | Vishwakarma2025Mapping | 2025 | primary | crop | F1 | L1p | M3 | none | none |
| 202 | Vlez2024Escayard | 2024 | dataset | crop | F1 | L1p | M4 | none | released |
| 203 | Vlez2025Framework | 2025 | primary | crop | F2 | L1p | M4 | none | none |
| 204 | Wang2023Electronic | 2023 | primary | livestock | F4 | L2 | M4 | comms | none |
| 205 | Wang2023Lightweight | 2023 | primary | livestock | F4 | L1p | M4 | none | released |
| 206 | Wang2023Variable | 2023 | primary | crop | F3 | L1a | M3 | compute | none |
| 207 | Wang2024Automated | 2024 | primary | livestock | F4 | L1p | M4 | none | released |
| 208 | Wang2024Development | 2024 | primary | crop | F3 | L1a | M3 | compute+comms | none |
| 209 | Wang2024Multispectral | 2024 | primary | crop | F1 | L1p | M3 | none | none |
| 210 | Wang2024Robust | 2024 | primary | crop | F1 | L1p | M3 | none | none |
| 211 | Wang2024Yield | 2024 | primary | crop | F2 | L1p | M4 | none | none |
| 212 | Wang2025Altitude | 2025 | primary | livestock | F4 | L1p | M4 | none | none |
| 213 | Wang2025Body | 2025 | primary | livestock | F4 | L1p | M4 | none | released |
| 214 | Wang2025Grazing | 2025 | primary | livestock | F4 | L1p | M4 | none | released |
| 215 | Wang2025Integrated | 2025 | dataset | livestock | F4 | L1p | M4 | none | released |
| 216 | Wang2025Multiple | 2025 | primary | crop | F1 | L1p | M3 | none | none |
| 217 | Wei2023Influences | 2023 | primary | crop | F3 | L1a | M4 | none | none |
| 218 | Wongsuk2024Spray | 2024 | primary | crop | F3 | L1a | M4 | none | none |
| 219 | Xiao2025Novel | 2025 | primary | cross-domain | F7 | L0 | M4 | compute | none |
| 220 | Xiu2025Fine | 2025 | primary | pasture | F4 | L1p | M4 | none | none |
| 221 | Xu2023Design | 2023 | primary | crop | F3 | L1a | M4 | energy | none |
| 222 | Xu2023Monitoring | 2023 | primary | crop | F1 | L1p | M3 | none | none |
| 223 | Yan2026Deep | 2026 | primary | livestock | F4 | L1p | M5 | none | none |
| 224 | Yang2024Assisted | 2024 | primary | crop | F1 | L1p | M3 | none | on request |
| 225 | Yang2025Direct | 2025 | primary | livestock | F4 | L1p | M4 | none | none |
| 226 | Yang2026Synchronous | 2026 | primary | crop | F3 | L1a | M3 | none | none |
| 227 | Ye2024Comparison | 2024 | primary | pasture | F1 | L1p | M4 | none | none |
| 228 | Yin2022Hyperspectral | 2022 | primary | crop | F1 | L1p | M3 | none | none |
| 229 | Zhang2023Evaluating | 2023 | primary | crop | F1 | L1p | M3 | none | none |
| 230 | Zhang2023Precision | 2023 | primary | crop | F3 | L4 | M2 | compute | none |
| 231 | Zhang2024Shortest | 2024 | primary | crop | F7 | L0 | M1 | none | none |
| 232 | Zhang2025Fast | 2025 | primary | crop | F6 | L0 | M1 | none | none |
| 233 | Zhang2026Automated | 2026 | primary | livestock | F4 | L1p | M4 | compute | none |
| 234 | Zhang2026Farmers | 2026 | primary | crop | F3 | L0 | M0 | none | none |
| 235 | Zhang2026Real | 2026 | primary | crop | F2 | L1p | M4 | compute+comms | none |
| 236 | Zhao2024Cotton | 2024 | primary | crop | F1 | L1p | M4 | none | none |
| 237 | Zhao2024Detecting | 2024 | primary | crop | F1 | L1p | M3 | none | none |
| 238 | Zhou2025Yield | 2025 | primary | crop | F1 | L1p | M3 | none | none |
| 239 | Zhou2026Endurance | 2026 | primary | crop | F7 | L0 | M1 | none | none |
| 240 | Zhu2025Utilizing | 2025 | primary | crop | F1 | L1p | M3 | none | none |
| 241 | Adam2025Deep | 2025 | survey | livestock | NA | NA | NA | NA | NA |
| 242 | Afridi2024Unveiling | 2024 | survey | wildlife-analogue | NA | NA | NA | NA | NA |
| 243 | Agrawal2024Transforming | 2024 | survey | crop | NA | NA | NA | NA | NA |
| 244 | Anam2024Systematic | 2024 | survey | crop | NA | NA | NA | NA | NA |
| 245 | Bernabucci2025Precision | 2025 | survey | livestock | NA | NA | NA | NA | NA |
| 246 | Bongomin2024Image | 2024 | survey | crop | NA | NA | NA | NA | NA |
| 247 | Borah2025Precision | 2025 | survey | crop | NA | NA | NA | NA | NA |
| 248 | Bretas2024Precision | 2024 | survey | pasture | NA | NA | NA | NA | NA |
| 249 | Cao2023Intelligent | 2023 | survey | livestock | NA | NA | NA | NA | NA |
| 250 | Caroppo2026Systematic | 2026 | survey | crop | NA | NA | NA | NA | NA |
| 251 | Dong2024Crop | 2024 | survey | crop | NA | NA | NA | NA | NA |
| 252 | Epifani2024Survey | 2024 | survey | crop | NA | NA | NA | NA | NA |
| 253 | Gong2025Edge | 2025 | survey | cross-domain | NA | NA | NA | NA | NA |
| 254 | Liu2022Challenges | 2022 | survey | crop | NA | NA | NA | NA | NA |
| 255 | Majumdar2024Enhancing | 2024 | survey | cross-domain | NA | NA | NA | NA | NA |
| 256 | Merz2022Autonomous | 2022 | survey | cross-domain | NA | NA | NA | NA | NA |
| 257 | Ren2024Integrating | 2024 | survey | cross-domain | NA | NA | NA | NA | NA |
| 258 | Rodimov2026Robotic | 2026 | survey | livestock | NA | NA | NA | NA | NA |
| 259 | Rong2026Research | 2026 | survey | crop | NA | NA | NA | NA | NA |
| 260 | Saini2025Review | 2025 | survey | crop | NA | NA | NA | NA | NA |
| 261 | Santos2024Vehicles | 2024 | survey | pasture | NA | NA | NA | NA | NA |
| 262 | Tanaka2024Review | 2024 | survey | crop | NA | NA | NA | NA | NA |
| 263 | Toscano2024Precision | 2024 | survey | crop | NA | NA | NA | NA | NA |
| 264 | Tzanidakis2023Precision | 2023 | survey | livestock | NA | NA | NA | NA | NA |
| 265 | VeraEsmeraldas2025Spectral | 2025 | survey | crop | NA | NA | NA | NA | NA |
| 266 | Yu2025Hyperspectral | 2025 | survey | crop | NA | NA | NA | NA | NA |
| 267 | Zhang2025Review | 2025 | survey | crop | NA | NA | NA | NA | NA |
| 268 | Zhu2024Intelligent | 2024 | survey | crop | NA | NA | NA | NA | NA |
| 269 | Arroyo2022Integrating | 2022 | generic_uav | cross-domain | NA | NA | NA | NA | NA |
| 270 | Poorvi2026Reliable | 2026 | generic_uav | cross-domain | NA | NA | NA | NA | NA |
| 271 | Zhang2022Optimization | 2022 | generic_uav | cross-domain | NA | NA | NA | NA | NA |

## 5. Bibliography

1. Afsar, Muhammad Munir; Iqbal, Muhammad Shahid; Bakhshi, Asim Dilawar; Hussain, Ejaz; Iqbal, Javed. MangiSpectra: A Multivariate Phenological Analysis Framework Leveraging UAV Imagery and LSTM for Tree Health and Yield Estimation in Mango Orchards. *Remote Sensing*, 2025. https://doi.org/10.3390/rs17040703
2. Ahmad, Wasim; Ali, Farman; Ullah, Yasir; Asghar Khan, Muhammad; Khan, Mansoor; Khan, Salabat; Attique Khan, Muhammad; Ali, Aitizaz; Almansour, Shahad. IoUT and Collaborative Cloud Computing-Based UAV Channel Modeling for Agriculture Communication. *IEEE Transactions on Consumer Electronics*, 2025. https://doi.org/10.1109/tce.2025.3593867
3. Ahmed, Mohamed A.; Gallardo, Jose Luis; Zuniga, Marcos D.; Pedraza, Manuel A.; Carvajal, Gonzalo; Jara, Nicolás; Carvajal, Rodrigo. LoRa Based IoT Platform for Remote Monitoring of Large-Scale Agriculture Farms in Chile. *Sensors*, 2022. https://doi.org/10.3390/s22082824
4. Akbari, Mohammad; Syed, Aisha; Kennedy, W. Sean; Erol-Kantarci, Melike. AoI-Aware Energy-Efficient SFC in UAV-Aided Smart Agriculture Using Asynchronous Federated Learning. *IEEE Open Journal of the Communications Society*, 2024. https://doi.org/10.1109/ojcoms.2024.3363132
5. Alanezi, Mohammed A.; Sadiq, Bashir O.; Sha’aban, Yusuf A.; Bouchekara, Houssem R. E. H. Livestock Management on Grazing Field: A FANET Based Approach. *Applied Sciences*, 2022. https://doi.org/10.3390/app12136654
6. Alanezi, Mohammed A.; Salami, Abdulazeez F.; Sha’aban, Yusuf A.; Bouchekara, Houssem R. E. H. RUBER: Recoverable UAV-based energy-efficient reconfigurable routing scheme for smart wireless livestock sensor network. *Frontiers in Energy Research*, 2022. https://doi.org/10.3389/fenrg.2022.975614
7. Alanezi, Mohammed A.; Salami, Abdulazeez F.; Sha’aban, Yusuf A.; Bouchekara, Houssem R. E. H.; Shahriar, Mohammad S.; Khodja, Mohammed; Smail, Mostafa K. UBER: UAV-Based Energy-Efficient Reconfigurable Routing Scheme for Smart Wireless Livestock Sensor Network. *Sensors*, 2022. https://doi.org/10.3390/s22166158
8. Almstedt, Lennart; Betti Sorbelli, Francesco; Boom, Bas; Calvini, Rosalba; Costi, Elena; Dinca, Alexandru; Ferrari, Veronica; Giannetti, Daniele; Ichim, Loretta; Kargar, Amin; Lazar, Catalin; Maistrello, Lara; Navarra, Alfredo; Niederprüm, David; Offermans, Peter; O'Flynn, Brendan; Palazzetti, Lorenzo; Patelli, Niccolò; Pinotti, Cristina M.; Popescu, Dan; Rangarajan, Aravind K.; Serghei, Liviu; Ulrici, Alessandro; Wolf, Lars; Zorbas, Dimitrios; Zurek, Leonard. Beyond the Naked Eye: Computer Vision for Detecting Brown Marmorated Stink Bug and Its Punctures. *IEEE Transactions on AgriFood Electronics*, 2025. https://doi.org/10.1109/tafe.2024.3429537
9. Almstedt, Lennart; Betti Sorbelli, Francesco; Boom, Bas; Calvini, Rosalba; Costi, Elena; Dinca, Alexandru; Ferrari, Veronica; Giannetti, Daniele; Ichim, Loretta; Kargar, Amin; Lazar, Catalin; Maistrello, Lara; Navarra, Alfredo; Niederprüm, David; Offermans, Peter; O'Flynn, Brendan; Palazzetti, Lorenzo; Patelli, Niccolò; Pinotti, Cristina M.; Popescu, Dan; Rangarajan, Aravind K.; Serghei, Liviu; Ulrici, Alessandro; Wolf, Lars; Zorbas, Dimitrios; Zurek, Leonard. A Comprehensive Pest Monitoring System for Brown Marmorated Stink Bug. *IEEE Transactions on AgriFood Electronics*, 2025. https://doi.org/10.1109/tafe.2024.3469538
10. Al-Najadi, Rawan; Al-Mulla, Yaseen; Al-Abri, Ibtisam; Al-Sadi, Abdullah Mohammed. Effectiveness of drone-based thermal sensors in optimizing controlled environment agriculture performance under arid conditions. *Scientific Reports*, 2025. https://doi.org/10.1038/s41598-025-94432-0
11. Amarasingam, Narmilan; Powell, Kevin; Sandino, Juan; Bratanov, Dmitry; Ashan Salgadoe, Arachchige Surantha; Gonzalez, Felipe. Mapping of insect pest infestation for precision agriculture: A UAV-based multispectral imaging and deep learning techniques. *International Journal of Applied Earth Observation and Geoinformation*, 2025. https://doi.org/10.1016/j.jag.2025.104413
12. Onler, Eray; Ozyurt, Hasan Berk; Sener, Mehmet; Arat, Sezen; Eker, Bulent; Celen, Ilker Huseyin. Spray Characterization of an Unmanned Aerial Vehicle for Agricultural Spraying. *The Philippine Agricultural Scientist*, 2023. https://doi.org/10.62550/ar007022
13. Anzai, Hiroki; Sakurai, Hina. Preliminary study on the application of robotic herding to manipulation of grazing distribution: Behavioral response of cattle to herding by an unmanned vehicle and its manipulation performance. *Applied Animal Behaviour Science*, 2022. https://doi.org/10.1016/j.applanim.2022.105751
14. Anzai, Hiroki; Kumaishi, Mahiro. Effects of continuous drone herding on behavioral response and spatial distribution of grazing cattle. *Applied Animal Behaviour Science*, 2023. https://doi.org/10.1016/j.applanim.2023.106089
15. Apostolidis, Savvas D.; Kapoutsis, Pavlos Ch.; Kapoutsis, Athanasios Ch.; Kosmatopoulos, Elias B. Cooperative multi-UAV coverage mission planning platform for remote sensing applications. *Autonomous Robots*, 2022. https://doi.org/10.1007/s10514-021-10028-3
16. Ariza-Sentís, Mar; Baja, Hilmy; Vélez, Sergio; Valente, João. Object detection and tracking on UAV RGB videos for early extraction of grape phenotypic traits. *Computers and Electronics in Agriculture*, 2023. https://doi.org/10.1016/j.compag.2023.108051
17. Baek, Jae‐Woon; Eun, Hye‐Ran; Kim, So‐Hee; Lee, Yoon‐Hee; Jeong, Mun‐Ju; Han, Xiongzhe; Min, Yi‐Gi; Noh, Hyun Ho; Shin, Yongho. Reduction of pesticide dosage and off‐target drift with enhanced control efficacy in unmanned aerial vehicle‐based application using lecithin adjuvants. *Pest Management Science*, 2026. https://doi.org/10.1002/ps.8551
18. Bakas, Khaoula; Saddik, Amine; Dliou, Azzedine; Hssaisoune, Mohammed; El Hachemy, Said; Ait-Ichou, Hamza; El Hafyani, Mohammed; Labbaci, Adnane; Bouchaou, Lhoussaine. UAV-based citrus tree segmentation, counting and yield estimation using lightweight deep learning approaches. *Smart Agricultural Technology*, 2025. https://doi.org/10.1016/j.atech.2025.101618
19. Bastos, Kécia M.; Barcelos, Jardel P.; Orioli, Guilherme F.; Nascimento, Sheila T. Use of Drones for Trough Reading, Animal Counting, and Production Monitoring in Feedlot Systems. *AgriEngineering*, 2024. https://doi.org/10.3390/agriengineering6040253
20. Benalaya, Najoua; Adjih, Cedric; Amdouni, Ichrak; Laouiti, Anis; Saidane, Leila. UAV Search Path Planning For Livestock Monitoring. *2022 IEEE 11th IFIP International Conference on Performance Evaluation and Modeling in Wireless and Wired Networks (PEMWN)*, 2022. https://doi.org/10.23919/pemwn56085.2022.9963839
21. Benalaya, Najoua; Amdouni, Ichrak; Adjih, Cedric; Laouiti, Anis; Saidane, Leila Azouz. Linear programming for UAVs search path planning in livestock health monitoring. *Computers and Electronics in Agriculture*, 2026. https://doi.org/10.1016/j.compag.2025.111232
22. Bertalan, László; Holb, Imre; Pataki, Angelika; Négyesi, Gábor; Szabó, Gergely; Kupásné Szalóki, Annamária; Szabó, Szilárd. UAV-based multispectral and thermal cameras to predict soil water content – A machine learning approach. *Computers and Electronics in Agriculture*, 2022. https://doi.org/10.1016/j.compag.2022.107262
23. Betti Sorbelli, Francesco; Palazzetti, Lorenzo; Pinotti, Cristina M. YOLO-based detection of Halyomorpha halys in orchards using RGB cameras and drones. *Computers and Electronics in Agriculture*, 2023. https://doi.org/10.1016/j.compag.2023.108228
24. Bian, Chaofa; Shi, Hongtao; Wu, Suqin; Zhang, Kefei; Wei, Meng; Zhao, Yindi; Sun, Yaqin; Zhuang, Huifu; Zhang, Xuewei; Chen, Shuo. Prediction of Field-Scale Wheat Yield Using Machine Learning Method and Multi-Spectral UAV Data. *Remote Sensing*, 2022. https://doi.org/10.3390/rs14061474
25. Bilal, Hazrat; Aslam, Muhammad Shamrooz; Tian, Yibin; Ullah, Inam; Ayouni, Sarra; Vasilakos, Athanasios V. A Consumer Electronics-Enhanced UAV System for Agricultural Farm Tracking With Fuzzy SMO and Actuator Fault Detection Control Algorithms. *IEEE Transactions on Consumer Electronics*, 2025. https://doi.org/10.1109/tce.2025.3563993
26. Biscamps, Jordi; Garcia-Ruiz, Francisco; Salcedo, Ramón; Salas, Bernat; Gil, Emilio. Laboratory and field comparison of onboard and remote sensors for canopy characterisation in vineyards. *Computers and Electronics in Agriculture*, 2025. https://doi.org/10.1016/j.compag.2025.110240
27. Blekanov, I.; Molin, A.; Zhang, D.; Mitrofanov, E.; Mitrofanova, O.; Li, Yin. Monitoring of grain crops nitrogen status from uav multispectral images coupled with deep learning approaches. *Computers and Electronics in Agriculture*, 2023. https://doi.org/10.1016/j.compag.2023.108047
28. Bokani, Ayub; Yadegaridehkordi, Elaheh; Kanhere, Salil S. LSTM-H: A Hybrid Deep Learning Model for Accurate Livestock Movement Prediction in UAV-Based Monitoring Systems. *Drones*, 2025. https://doi.org/10.3390/drones9050346
29. Boubin, Jayson; Zhang, Zichen; Chumley, John; Stewart, Christopher. Adaptive Deployment for Autonomous Agricultural UAV Swarms. *Proceedings of the 20th ACM Conference on Embedded Networked Sensor Systems*, 2022. https://doi.org/10.1145/3560905.3568414
30. Bouchekara, Houssem R. E. H.; Sadiq, Bashir O; O Zakariyya, Sikiru; Sha’aban, Yusuf A.; Shahriar, Mohammad S.; Isah, Musab M. SIFT-CNN Pipeline in Livestock Management: A Drone Image Stitching Algorithm. *Drones*, 2022. https://doi.org/10.3390/drones7010017
31. Bouchekara, Houssem R. E. H.; Salami, Abdulazeez F.; Sha’aban, Yusuf A.; Nahas, Mouaaz; Shahriar, Mohammad S.; Alanezi, Mohammed A. TUBER: Time-aware UAV-based energy-efficient reconfigurable routing scheme for smart wireless livestock sensor network. *PLOS ONE*, 2024. https://doi.org/10.1371/journal.pone.0292301
32. Bárbulo Barrios, Diego; Valente, João; van Langevelde, Frank. Monitoring mammalian herbivores via convolutional neural networks implemented on thermal UAV imagery. *Computers and Electronics in Agriculture*, 2024. https://doi.org/10.1016/j.compag.2024.108713
33. Bukowiecki, Josephine; Rose, Till; Holzhauser, Katja; Rothardt, Steffen; Rose, Maren; Komainda, Martin; Herrmann, Antje; Kage, Henning. UAV-based canopy monitoring: calibration of a multispectral sensor for green area index and nitrogen uptake across several crops. *Precision Agriculture*, 2024. https://doi.org/10.1007/s11119-024-10123-2
34. Burchard-Levine, V.; Guerra, J. G.; Borra-Serrano, I.; Nieto, H.; Mesías-Ruiz, G.; Dorado, J.; de Castro, A. I.; Herrezuelo, M.; Mary, B.; Aguirre, E. P.; Peña, J. M. Evaluating the utility of combining high resolution thermal, multispectral and 3D imagery from unmanned aerial vehicles to monitor water stress in vineyards. *Precision Agriculture*, 2024. https://doi.org/10.1007/s11119-024-10179-0
35. Burchard-Levine, V.; Borra-Serrano, I.; Peña, J. M.; Kustas, W. P.; Guerra, J. G.; Dorado, J.; Mesías-Ruiz, G.; Herrezuelo, M.; Mary, B.; McKee, L. M.; de Castro, A. I.; Sanchez-Élez, S.; Nieto, H. Evaluating the precise grapevine water stress detection using unmanned aerial vehicles and evapotranspiration-based metrics. *Irrigation Science*, 2025. https://doi.org/10.1007/s00271-024-00931-9
36. Calderone, Giulio; Molins, Mireia; Catania, Pietro; Boney, John; Casella, Enrico. Aerial monitoring of turkey behavior using unmanned aerial vehicles and computer vision. *Poultry Science*, 2025. https://doi.org/10.1016/j.psj.2025.106103
37. Cantürk, Meltem; Zabawa, Laura; Pavlic, Diana; Dreier, Ansgar; Klingbeil, Lasse; Kuhlmann, Heiner. UAV-based individual plant detection and geometric parameter extraction in vineyards. *Frontiers in Plant Science*, 2023. https://doi.org/10.3389/fpls.2023.1244384
38. Carracelas, Gonzalo; Ballester, Carlos; Marchesi, Claudia; Roel, Alvaro; Hornbuckle, John. Assessing Drone-Based Remote Sensing Indices for Monitoring Rice Nitrogen Plant Status Under Different Irrigation Techniques. *Agronomy*, 2024. https://doi.org/10.3390/agronomy14122976
39. Castro, Gabriel G. R. de; Berger, Guido S.; Cantieri, Alvaro; Teixeira, Marco; Lima, José; Pereira, Ana I.; Pinto, Milena F. Adaptive Path Planning for Fusing Rapidly Exploring Random Trees and Deep Reinforcement Learning in an Agriculture Dynamic Environment UAVs. *Agriculture*, 2023. https://doi.org/10.3390/agriculture13020354
40. Catala-Roman, Paula; Segura-Garcia, Jaume; Dura, Esther; Navarro-Camba, Enrique A.; Alcaraz-Calero, Jose M.; Garcia-Pineda, Miguel. AI-based autonomous UAV swarm system for weed detection and treatment: Enhancing organic orange orchard efficiency with agriculture 5.0. *Internet of Things*, 2024. https://doi.org/10.1016/j.iot.2024.101418
41. Chen, Pengchao; Ouyang, Fan; Zhang, Yali; Lan, Yubin. Preliminary Evaluation of Spraying Quality of Multi-Unmanned Aerial Vehicle (UAV) Close Formation Spraying. *Agriculture*, 2022. https://doi.org/10.3390/agriculture12081149
42. Chen, Teng-Yu; Miao, Zhong-Hua; Li, Wei-Min; Pan, Quan-Ke. A learning-based memetic algorithm for a cooperative task allocation problem of multiple unmanned aerial vehicles in smart agriculture. *Swarm and Evolutionary Computation*, 2024. https://doi.org/10.1016/j.swevo.2024.101694
43. Chen, Yini; Gao, Ronghua; Li, Qifeng; Zhao, Hongtao; Wang, Rong; Ding, Luyu; Li, Xuwen. DASNet a dual branch multi level attention sheep counting network. *Scientific Reports*, 2025. https://doi.org/10.1038/s41598-025-97929-w
44. Chen, Wenbo; Wang, Dongliang; Xie, Xiaowei. An Efficient Algorithm for Small Livestock Object Detection in Unmanned Aerial Vehicle Imagery. *Animals*, 2025. https://doi.org/10.3390/ani15121794
45. Chen, Pengchao; Ma, Haoran; Cui, Zongyin; Li, Zhihong; Wu, Jiapei; Liao, Jianhong; Liu, Hanbing; Wang, Ying; Lan, Yubin. Field Study of UAV Variable-Rate Spraying Method for Orchards Based on Canopy Volume. *Agriculture*, 2025. https://doi.org/10.3390/agriculture15131374
46. Chen, Xue; Wang, Changling; Zhao, Mingyu; Zhu, Zhaoyan; Zhu, Tong; Gao, Jingyi; Wu, Junxue; Han, Jiajun; Zhao, Fanrong; Wang, Kai. Pesticide spray drift and risk assessment using unmanned aerial vehicle (UAV) sprayer and traditional electric knapsack sprayer (EKS). *Science of The Total Environment*, 2025. https://doi.org/10.1016/j.scitotenv.2025.180866
47. Chen, Jingyang; Li, Xiaohui; Cai, Bin; He, Jie; Ma, Yajie; Liu, Jun. A Reinforcement-Learning-Based Energy Charging Strategy for Agricultural Internet of Things With Multi-UAV-Assisted WRSN. *IEEE Internet of Things Journal*, 2025. https://doi.org/10.1109/jiot.2025.3569384
48. Cheng, Minghan; Sun, Chengming; Nie, Chenwei; Liu, Shuaibing; Yu, Xun; Bai, Yi; Liu, Yadong; Meng, Lin; Jia, Xiao; Liu, Yuan; Zhou, Lili; Nan, Fei; Cui, Tengyu; Jin, Xiuliang. Evaluation of UAV-based drought indices for crop water conditions monitoring: A case study of summer maize. *Agricultural Water Management*, 2023. https://doi.org/10.1016/j.agwat.2023.108442
49. Chittoor, Prithvi Krishna; Chokkalingam, Bharatiraja; Verma, Rajesh; Mihet-Popa, Lucian. An Assessment of Shortest Prioritized Path-Based Bidirectional Wireless Charging Approach Toward Smart Agriculture. *IEEE Access*, 2023. https://doi.org/10.1109/access.2023.3329976
50. Chou, Shih-Fan; Liao, Chao-Hsiang. Energy-Efficient UAV Path Planning and Charging Integration for Precision Agriculture. *2025 IEEE VTS Asia Pacific Wireless Communications Symposium (APWCS)*, 2025. https://doi.org/10.1109/apwcs67981.2025.11151947
51. Cui, Beibei; Liang, Liang; Ji, Baofeng; Zhang, Lei; Zhao, Liang; Zhang, Kunpeng; Shi, Fengzheng; Créput, Jean-Charles. Exploring the YOLO-FT Deep Learning Algorithm for UAV-Based Smart Agriculture Detection in Communication Networks. *IEEE Transactions on Network and Service Management*, 2024. https://doi.org/10.1109/tnsm.2024.3424232
52. Dadallage, Keshawa M.; Amogi, Basavaraj R.; Khot, Lav R.; Leal Yepes, Francisco A. Mask R-CNN and Centroid Tracking Algorithm to Process UAV Based Thermal-RGB Video for Drylot Cattle Heat Stress Monitoring. *Drones*, 2024. https://doi.org/10.3390/drones8090491
53. de Lima Weber, Fabricio; de Moraes Weber, Vanessa Aparecida; de Moraes, Pedro Henrique; Matsubara, Edson Takashi; Paiva, Débora Maria Barroso; de Nadai Bonin Gomes, Marina; de Oliveira, Luiz Orcírio Fialho; de Medeiros, Sérgio Raposo; Cagnin, Maria Istela. Counting cattle in UAV images using convolutional neural network. *Remote Sensing Applications: Society and Environment*, 2023. https://doi.org/10.1016/j.rsase.2022.100900
54. Divazi, Arash; Askari, Rasoul; Roohi, Ehsan. Experimental and numerical investigation on the spraying performance of an agricultural unmanned aerial vehicle. *Aerospace Science and Technology*, 2025. https://doi.org/10.1016/j.ast.2025.110083
55. Duan, Jiaming; Rudnick, Daran R.; Proctor, Christopher A.; Heeren, Derek; Nakabuye, Hope Njuki; Katimbo, Abia; Shi, Yeyin; de Sousa Ferreira, Victor. Estimation of corn nitrogen demand under different irrigation conditions based on UAV multispectral technology. *Agricultural Water Management*, 2024. https://doi.org/10.1016/j.agwat.2024.109075
56. Duttenhefner, Jessica L.; Greives, Timothy J.; Klug, Page E. Spraying drones: efficacy of integrating an avian repellent with drone hazing to elicit blackbird flock dispersal and abandonment of sunflower fields. *Wildlife Biology*, 2024. https://doi.org/10.1002/wlb3.01333
57. Ergunsah, Senol; Tümen, Vedat; Kosunalp, Selahattin; Demir, Kubilay. Energy‐efficient animal tracking with multi‐unmanned aerial vehicle path planning using reinforcement learning and wireless sensor networks. *Concurrency and Computation: Practice and Experience*, 2023. https://doi.org/10.1002/cpe.7527
58. Eun, Hye-Ran; Kim, So-Hee; Lee, Yoon-Hee; Kim, Su-Min; Lee, Ye-Jin; Jung, Hee-Young; Min, Yi-Gi; Noh, Hyun Ho; Shin, Yongho. Comparison of off-target pesticide drift in paddy fields from unmanned aerial vehicle spraying using cellulose deposition sampler. *Ecotoxicology and Environmental Safety*, 2024. https://doi.org/10.1016/j.ecoenv.2024.117075
59. Fahad, Nur Mohammad; Thuseethan, Selvarajah; Azid, Sheikh Izzal; Azam, Sami. An Innovative Coverage Path Planning Approach for UAVs to Boost Precision Agriculture and Rescue Operations. *International Journal of Intelligent Systems*, 2025. https://doi.org/10.1155/int/4700518
60. Fendji, Jean Louis Ebongue Kedieng; Bayaola, Israel Kolaigue; Thron, Christopher; Fendji, Marie Danielle; Förster, Anna. Cost-Effective Placement of Recharging Stations in Drone Path Planning for Surveillance Missions on Large Farms. *Symmetry*, 2020. https://doi.org/10.3390/sym12101661
61. Fu, Haitao; Li, Zheng; Zhang, Weijian; Feng, Yuxuan; Zhu, Li; Fang, Xu; Li, Jian. Research on Path Planning of Agricultural UAV Based on Improved Deep Reinforcement Learning. *Agronomy*, 2024. https://doi.org/10.3390/agronomy14112669
62. Ganeva, Dessislava; Roumenina, Eugenia; Dimitrov, Petar; Gikov, Alexander; Jelev, Georgi; Dragov, Rangel; Bozhanova, Violeta; Taneva, Krasimira. Phenotypic Traits Estimation and Preliminary Yield Assessment in Different Phenophases of Wheat Breeding Experiment Based on UAV Multispectral Images. *Remote Sensing*, 2022. https://doi.org/10.3390/rs14041019
63. Gao, Jerry; Bambrah, Charanjit Kaur; Parihar, Nidhi; Kshirsagar, Sharvaree; Mallarapu, Sruthi; Yu, Hailong; Wu, Jane; Yang, Yunyun. Analysis of Various Machine Learning Algorithms for Using Drone Images in Livestock Farms. *Agriculture*, 2024. https://doi.org/10.3390/agriculture14040522
64. Giannetti, Daniele; Patelli, Niccolò; Palazzetti, Lorenzo; Betti Sorbelli, Francesco; Pinotti, Cristina M.; Maistrello, Lara. First use of unmanned aerial vehicles to monitor Halyomorpha halys and recognize it using artificial intelligence. *Pest Management Science*, 2024. https://doi.org/10.1002/ps.8115
65. Güneş, Doğan; Hasegawa, Hideo. Optimizing UAV sprayer performance using field data and machine learning approaches. *Smart Agricultural Technology*, 2025. https://doi.org/10.1016/j.atech.2025.101013
66. Guo, Yahui; Hao, Fanghua; Zhang, Xuan; He, Yuhong; Fu, Yongshuo H. Improving maize yield estimation by assimilating UAV-based LAI into WOFOST model. *Field Crops Research*, 2024. https://doi.org/10.1016/j.fcr.2024.109477
67. Guo, Zhonghui; Cai, Dongdong; Bai, Juchi; Xu, Tongyu; Yu, Fenghua. Intelligent Rice Field Weed Control in Precision Agriculture: From Weed Recognition to Variable Rate Spraying. *Agronomy*, 2024. https://doi.org/10.3390/agronomy14081702
68. Guo, Xihong; Feng, Quan; Guo, Faxu. CMTNet: a hybrid CNN-transformer network for UAV-based hyperspectral crop classification in precision agriculture. *Scientific Reports*, 2025. https://doi.org/10.1038/s41598-025-97052-w
69. Hegde, Aditya; Ghose, Debasish. Multi-Quadrotor Distributed Load Transportation for Autonomous Agriculture Spraying Operations. *Journal of Guidance, Control, and Dynamics*, 2022. https://doi.org/10.2514/1.g006608
70. Hijikata, Daisuke; Suenaga, Masaya; Lu, Zhiyuan; Uto, Kuniaki; Hatanaka, Takeshi. Hierarchical coverage scheduling and control over geographically dispersed farmlands with multi‐drone systems. *Asian Journal of Control*, 2026. https://doi.org/10.1002/asjc.70139
71. Hobart, Marius; Pflanz, Michael; Tsoulias, Nikos; Weltzien, Cornelia; Kopetzky, Mia; Schirrmann, Michael. Fruit Detection and Yield Mass Estimation from a UAV Based RGB Dense Cloud for an Apple Orchard. *Drones*, 2025. https://doi.org/10.3390/drones9010060
72. Holtorf, Lucas; Titov, Igor; Daschner, Frank; Gerken, Martina. UAV-Based Wireless Data Collection from Underground Sensor Nodes for Precision Agriculture. *AgriEngineering*, 2023. https://doi.org/10.3390/agriengineering5010022
73. Hütt, Christoph; Bolten, Andreas; Hüging, Hubert; Bareth, Georg. UAV LiDAR Metrics for Monitoring Crop Height, Biomass and Nitrogen Uptake: A Case Study on a Winter Wheat Field Trial. *PFG – Journal of Photogrammetry, Remote Sensing and Geoinformation Science*, 2023. https://doi.org/10.1007/s41064-022-00228-6
74. Hütt, Christoph; Isselstein, Johannes; Komainda, Martin; Schöttker, Oliver; Sturm, Astrid. UAV LiDAR-based grassland biomass estimation for precision livestock management. *Journal of Applied Remote Sensing*, 2024. https://doi.org/10.1117/1.jrs.18.017502
75. Hua, Lianghao; Zhang, Jianfeng; Li, Dejie; Xi, Xiaobo. Fault-Tolerant Active Disturbance Rejection Control of Plant Protection of Unmanned Aerial Vehicles Based on a Spatio-Temporal RBF Neural Network. *Applied Sciences*, 2021. https://doi.org/10.3390/app11094084
76. Hua, Lianghao; Zhang, Jianfeng; Li, Dejie; Xi, Xiaobo. Fractional Gradient Descent RBFNN for Active Fault-Tolerant Control of Plant Protection UAVs. *Computer Modeling in Engineering & Sciences*, 2024. https://doi.org/10.32604/cmes.2023.030535
77. Huang, Jing; Luo, Yao; Quan, Quan; Wang, Ban; Xue, Xianghong; Zhang, Youmin. An autonomous task assignment and decision-making method for coverage path planning of multiple pesticide spraying UAVs. *Computers and Electronics in Agriculture*, 2023. https://doi.org/10.1016/j.compag.2023.108128
78. Huang, Qian; Yang, Jun; Yang, Mengqi; Jiang, Dan; Wang, Tan. DMN-YOLO: A Lightweight Small-Object Detector for Multi-Species Animal Detection in UAV Grassland Imagery. *Animals*, 2026. https://doi.org/10.3390/ani16111643
79. Hussain, Saddam; Arshad, Muhammad; Cheema, Muhammad Jehanzeb Masud; Qamar, Muhammad Uzair; Wajid, Syed Aftab; Daccache, Andre. Advancing Soil Moisture Prediction Using Satellite and UAV-based Imagery with Machine Learning Models. *Earth Systems and Environment*, 2026. https://doi.org/10.1007/s41748-025-00761-5
80. Hwerbi, Khouloud; Amdouni, Ichrak; Laouiti, Anis; Adjih, Cedric; Saidane, Leila. Veterinary Drone: Blockchain-Based System for Cattle Health Monitoring. *2023 International Wireless Communications and Mobile Computing (IWCMC)*, 2023. https://doi.org/10.1109/iwcmc58020.2023.10182480
81. Ijaz, Salman; Shi, Yuhao; Khan, Yasir Ali; Khodaverdian, Maria; Javaid, Umair. Robust adaptive control law design for enhanced stability of agriculture UAV used for pesticide spraying. *Aerospace Science and Technology*, 2024. https://doi.org/10.1016/j.ast.2024.109676
82. Impollonia, Giorgio; Croci, Michele; Ferrarini, Andrea; Brook, Jason; Martani, Enrico; Blandinières, Henri; Marcone, Andrea; Awty-Carroll, Danny; Ashman, Chris; Kam, Jason; Kiesel, Andreas; Trindade, Luisa M.; Boschetti, Mirco; Clifton-Brown, John; Amaducci, Stefano. UAV Remote Sensing for High-Throughput Phenotyping and for Yield Prediction of Miscanthus by Machine Learning Techniques. *Remote Sensing*, 2022. https://doi.org/10.3390/rs14122927
83. Islam, Md Didarul; Liu, Wenxin; Izere, Pascal; Singh, Puranjit; Yu, Chong; Riggan, Benjamin; Zhang, Kuan; Jhala, Amit J.; Knezevic, Stevan; Ge, Yufeng; Pitla, Santosh; Luck, Joe; Shi, Yeyin. Towards real-time weed detection and segmentation with lightweight CNN models on edge devices. *Computers and Electronics in Agriculture*, 2025. https://doi.org/10.1016/j.compag.2025.110600
84. Jasim, Ali Najm; Fourati, Lamia Chaari; Albahri, O. S. Evaluation of Unmanned Aerial Vehicles for Precision Agriculture Based on Integrated Fuzzy Decision-Making Approach. *IEEE Access*, 2023. https://doi.org/10.1109/access.2023.3294094
85. Jawad, Aqeel Mahmood; Jawad, Haider Mahmood; Nordin, Rosdiadee; Gharghan, Sadik Kamel; Abdullah, Nor Fadzilah; Abu-Alshaeer, Mahmood Jawad. Wireless Power Transfer With Magnetic Resonator Coupling and Sleep/Active Strategy for a Drone Charging Station in Smart Agriculture. *IEEE Access*, 2019. https://doi.org/10.1109/access.2019.2943120
86. Jeon, Dasom; Jung, Hyun-jin; Lee, Kyung-do; Han, JungGon; Park, Chanwon; Han, Seunghoon; Kim, Hojin. A Study of Spray Volume Prediction Techniques for Variable Rate Pesticide Application using Unmanned Aerial Vehicles. *Journal of Biosystems Engineering*, 2025. https://doi.org/10.1007/s42853-024-00249-6
87. Ji, Yishan; Chen, Zhen; Cheng, Qian; Liu, Rong; Li, Mengwei; Yan, Xin; Li, Guan; Wang, Dong; Fu, Li; Ma, Yu; Jin, Xiuliang; Zong, Xuxiao; Yang, Tao. Estimation of plant height and yield based on UAV imagery in faba bean (Vicia faba L.). *Plant Methods*, 2022. https://doi.org/10.1186/s13007-022-00861-7
88. Ji, Wenxiang; Luo, Yifei; Liao, Yafang; Wu, Wenjun; Wei, Xinyi; Yang, Yudie; He, Xiong Zhao; Shen, Yutong; Ma, Qingshan; Yi, Shuhua; Sun, Yi. UAV Assisted Livestock Distribution Monitoring and Quantification: A Low-Cost and High-Precision Solution. *Animals*, 2023. https://doi.org/10.3390/ani13193069
89. Jiang, Jianfeng. Wind Disturbance Rejection Technology for Quadrotor UAVs in Farmland Irrigation Applications. *Science and Technology of Engineering, Chemistry and Environmental Protection*, 2025. https://doi.org/10.61173/drvrcj85
90. Jinyu, Liu; Esyin, Chew; Chow, Siing Sia; Hasyiya, Karimah Adli; Linnan, Zhang; Shichen, Gai; Jiaji, Yang; Tao, Wang. Robotic herding framework design for remote and small-scale pastoral farming. *International Journal of Agricultural and Biological Engineering*, 2025. https://doi.org/10.25165/j.ijabe.20251806.9826
91. Kaushal, Swas; Gill, Harsimardeep S.; Billah, Mohammad Maruf; Khan, Shahid Nawaz; Halder, Jyotirmoy; Bernardo, Amy; Amand, Paul St.; Bai, Guihua; Glover, Karl; Maimaitijiang, Maitiniyazi; Sehgal, Sunish K. Enhancing the potential of phenomic and genomic prediction in winter wheat breeding using high-throughput phenotyping and deep learning. *Frontiers in Plant Science*, 2024. https://doi.org/10.3389/fpls.2024.1410249
92. Khan, Shahbaz; Tufail, Muhammad; Khan, Muhammad Tahir; Khan, Zubair Ahmad; Iqbal, Javaid; Wasim, Arsalan. Real-time recognition of spraying area for UAV sprayers using a deep learning approach. *PLOS ONE*, 2021. https://doi.org/10.1371/journal.pone.0249436
93. Khose, Suyog Balasaheb; Mailapalli, Damodhara Rao. Spatial mapping of soil moisture content using very-high resolution UAV-based multispectral image analytics. *Smart Agricultural Technology*, 2024. https://doi.org/10.1016/j.atech.2024.100467
94. Killeen, Patrick; Kiringa, Iluju; Yeap, Tet; Branco, Paula. Corn Grain Yield Prediction Using UAV-Based High Spatiotemporal Resolution Imagery, Machine Learning, and Spatial Cross-Validation. *Remote Sensing*, 2024. https://doi.org/10.3390/rs16040683
95. Kim, Sang-Bum; Lee, Sang-Hyun. Battery Balancing Algorithm for an Agricultural Drone Using a State-of-Charge-Based Fuzzy Controller. *Applied Sciences*, 2020. https://doi.org/10.3390/app10155277
96. Kim, Chang Jo; Yuan, Xiu; Kim, Min; Kyung, Kee Sung; Noh, Hyun Ho. Monitoring and risk analysis of residual pesticides drifted by unmanned aerial spraying. *Scientific Reports*, 2023. https://doi.org/10.1038/s41598-023-36822-w
97. King, Andrew J.; Portugal, Steven J.; Strömbom, Daniel; Mann, Richard P.; Carrillo, José A.; Kalise, Dante; de Croon, Guido; Barnett, Heather; Scerri, Paul; Groß, Roderich; Chadwick, David R.; Papadopoulou, Marina. Biologically inspired herding of animal groups by robots. *Methods in Ecology and Evolution*, 2023. https://doi.org/10.1111/2041-210x.14049
98. Kizielewicz, Bartłomiej; Wątróbski, Jarosław; Sałabun, Wojciech. Multi-criteria decision support system for the evaluation of UAV intelligent agricultural sensors. *Artificial Intelligence Review*, 2025. https://doi.org/10.1007/s10462-025-11201-1
99. Kodors, Sergejs; Zarembo, Imants; Lācis, Gunārs; Litavniece, Lienīte; Apeināns, Ilmārs; Sondors, Marks; Pacejs, Antons. Autonomous Yield Estimation System for Small Commercial Orchards Using UAV and AI. *Drones*, 2024. https://doi.org/10.3390/drones8120734
100. Koshelev, Iaroslav; Savinov, Maxim; Menshchikov, Alexander; Somov, Andrey. Drone-Aided Detection of Weeds: Transfer Learning for Embedded Image Processing. *IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing*, 2023. https://doi.org/10.1109/jstars.2022.3224657
101. Krestenitis, Marios; Raptis, Emmanuel K.; Kapoutsis, Athanasios Ch.; Ioannidis, Konstantinos; Kosmatopoulos, Elias B.; Vrochidis, Stefanos. Overcome the Fear Of Missing Out: Active sensing UAV scanning for precision agriculture. *Robotics and Autonomous Systems*, 2024. https://doi.org/10.1016/j.robot.2023.104581
102. Kuang, Xiaohui; Cheng, Qian; Chen, Deshan; Fu, Wanna; Li, Hao; Chen, Zhen. Intelligent diagnosis of winter wheat water stress based on UAV multi-modal remote sensing. *Smart Agricultural Technology*, 2026. https://doi.org/10.1016/j.atech.2026.101781
103. Kumar, Ashish; Behera, Laxmidhar. Design, Localization, Perception, and Control for GPS-Denied Autonomous Aerial Grasping and Harvesting. *IEEE Robotics and Automation Letters*, 2024. https://doi.org/10.1109/lra.2024.3366015
104. Kutyrev, Alexey; Khort, Dmitry; Smirnov, Igor; Zubina, Valeria. UAV-based sustainable orchard management: Deep learning for apple detection and yield estimation. *E3S Web of Conferences*, 2025. https://doi.org/10.1051/e3sconf/202561403021
105. Lacerda, Lorena N.; Snider, John L.; Cohen, Yafit; Liakos, Vasileios; Gobbo, Stefano; Vellidis, George. Using UAV-based thermal imagery to detect crop water status variability in cotton. *Smart Agricultural Technology*, 2022. https://doi.org/10.1016/j.atech.2021.100029
106. Lambertini, Alessandro; Mandanici, Emanuele; Tini, Maria Alessandra; Vittuari, Luca. Technical Challenges for Multi-Temporal and Multi-Sensor Image Processing Surveyed by UAV for Mapping and Monitoring in Precision Agriculture. *Remote Sensing*, 2022. https://doi.org/10.3390/rs14194954
107. Lan, Xinguo; Wang, Juan; Chen, Pengchao; Liang, Qifu; Zhang, Linjia; Ma, Chao. Risk assessment of environmental and bystander exposure from agricultural unmanned aerial vehicle sprayers in golden coconut plantations: Effects of droplet size and spray volume. *Ecotoxicology and Environmental Safety*, 2024. https://doi.org/10.1016/j.ecoenv.2024.116675
108. Lara-Molina, Fabian Andres. Optimization of Coverage Path Planning for Agricultural Drones in Weed-Infested Fields Using Semantic Segmentation. *Agriculture*, 2025. https://doi.org/10.3390/agriculture15121262
109. Laroche-Pinel, E.; Vasquez, K. R.; Brillante, L. Assessing grapevine water status in a variably irrigated vineyard with NIR/SWIR hyperspectral imaging from UAV. *Precision Agriculture*, 2024. https://doi.org/10.1007/s11119-024-10170-9
110. Lee, Hyeon-Seung; Shin, Beom-Soo; Thomasson, J. Alex; Wang, Tianyi; Zhang, Zhao; Han, Xiongzhe. Development of Multiple UAV Collaborative Driving Systems for Improving Field Phenotyping. *Sensors*, 2022. https://doi.org/10.3390/s22041423
111. Li, Longlong; Hu, Zhihong; Liu, Qingju; Yi, Tongchuan; Han, Ping; Zhang, Ruirui; Pan, Ligang. Effect of flight velocity on droplet deposition and drift of combined pesticides sprayed using an unmanned aerial vehicle sprayer in a peach orchard. *Frontiers in Plant Science*, 2022. https://doi.org/10.3389/fpls.2022.981494
112. Li, Jiyu; Long, Bo; Wu, Han; Hu, Xiaodan; Wei, Xu; Zhang, Zhixun; Chai, Lin; Xie, Jindian; Mei, Huilan. Rapid Evaluation Model of Endurance Performance and Its Application for Agricultural UAVs. *Drones*, 2022. https://doi.org/10.3390/drones6080186
113. Li, Xiaohui; Huang, Hailong; Savkin, Andrey; Zhang, Jian. Robotic Herding of Farm Animals Using a Network of Barking Aerial Drones. *Drones*, 2022. https://doi.org/10.3390/drones6020029
114. Li, Fei; Bai, Jingya; Zhang, Mengyun; Zhang, Ruoyu. Yield estimation of high-density cotton fields using low-altitude UAV imaging and deep learning. *Plant Methods*, 2022. https://doi.org/10.1186/s13007-022-00881-3
115. Li, Jiacheng; Sheng, Hanlin; Zhang, Jie; Zhang, Haibo. Coverage Path Planning Method for Agricultural Spraying UAV in Arbitrary Polygon Area. *Aerospace*, 2023. https://doi.org/10.3390/aerospace10090755
116. Li, Lei; Hassan, Muhammad Adeel; Song, Jie; Xie, Yongdun; Rasheed, Awais; Yang, Shurong; Li, Hongye; Liu, Peng; Xia, Xianchun; He, Zhonghu; Xiao, Yonggui. UAV‐based RGB imagery and ground measurements for high‐throughput phenotyping of senescence and QTL mapping in bread wheat. *Crop Science*, 2023. https://doi.org/10.1002/csc2.21086
117. Li, Denghui; Sun, Xiaoxuan; Jia, Yuhang; Yao, Zhongwei; Lin, Peiyi; Chen, Yingyi; Zhou, Haobo; Zhou, Zhengqi; Wu, Kaixuan; Shi, Linlin; Li, Jun. A longan yield estimation approach based on UAV images and deep learning. *Frontiers in Plant Science*, 2023. https://doi.org/10.3389/fpls.2023.1132909
118. Li, Kangshun; Xie, Shumin; Zhu, Tianjin; Wang, Hui. Constrained Multiobjective Optimization for UAV-Assisted Mobile Edge Computing in Smart Agriculture: Minimizing Delay and Energy Consumption. *IEEE Transactions on Sustainable Computing*, 2024. https://doi.org/10.1109/tsusc.2024.3401003
119. Li, Haoran; Li, Ying; Zeeshan, Muhammad; Yang, Longfei; Gao, Zhishuo; Yang, Yuting; Zhang, Guoqiang; Wang, Chunjuan; Han, Xiaoqiang. The Influence of Unmanned Aerial Vehicle Wind Field on the Pesticide Droplet Deposition and Control Effect in Cotton Fields. *Agronomy*, 2025. https://doi.org/10.3390/agronomy15051221
120. Lin, Yongda; Chen, Tingting; Liu, Shiyuan; Cai, Yulin; Shi, Haowen; Zheng, Dike; Lan, Yubin; Yue, Xuejun; Zhang, Lei. Quick and accurate monitoring peanut seedlings emergence rate through UAV video and deep learning. *Computers and Electronics in Agriculture*, 2022. https://doi.org/10.1016/j.compag.2022.106938
121. Lin, Q.; Dubinin, S. V.; Wu, L.-Ch.; Wang, K.-K.; Li, X.-L.; Wang, Q.-L. Optimization and thermal management of battery power supply system for agricultural drones. *«System analysis and applied information science»*, 2025. https://doi.org/10.21122/2309-4923-2025-4-26-35
122. Lipovac, Aleksa; Bezdan, Atila; Moravčević, Djordje; Djurović, Nevenka; Ćosić, Marija; Benka, Pavel; Stričević, Ružica. Correlation between Ground Measurements and UAV Sensed Vegetation Indices for Yield Prediction of Common Bean Grown under Different Irrigation Treatments and Sowing Periods. *Water*, 2022. https://doi.org/10.3390/w14223786
123. Lishchynskyi, Maksym; Cheng, Irene; Nikolaidis, Ioanis. Trajectory Agnostic Livestock Counting Through UAV Imaging. *2024 IEEE 21st International Conference on Mobile Ad-Hoc and Smart Systems (MASS)*, 2024. https://doi.org/10.1109/mass62177.2024.00109
124. Liu, Tao; Zhang, Baohua; Tan, Qianqiu; Zhou, Jun; Yu, Shuwan; Zhu, Qingzhen; Bian, Yifan. Immersive human-machine teleoperation framework for precision agriculture: Integrating UAV-based digital mapping and virtual reality control. *Computers and Electronics in Agriculture*, 2024. https://doi.org/10.1016/j.compag.2024.109444
125. Liu, Zongru; Gao, Rong; Zhao, Yinwei; Wu, Han; Liang, Yunting; Liang, Ke; Liu, Dong; Huang, Taoran; Xie, Shaoqiang; Lv, Jia; Li, Jiyu. Study on the Characteristics of Downwash Field Range and Consistency of Spray Deposition of Agricultural UAVs. *Agriculture*, 2024. https://doi.org/10.3390/agriculture14060931
126. Liu, Xuhang; Liu, Yicheng; Chen, Xinhanyang; Wan, Yuhan; Gao, Dengxi; Cao, Pei. LiDAR-Assisted UAV Variable-Rate Spraying System. *Agriculture*, 2025. https://doi.org/10.3390/agriculture15161782
127. Liu, Lingling; Wang, Aimin; Sun, Geng; Li, Jiahui; Pan, Hongyang; Quek, Tony Q. S. Multi-Objective Optimization for Data Collection in UAV-Assisted Agricultural IoT. *IEEE Transactions on Vehicular Technology*, 2025. https://doi.org/10.1109/tvt.2024.3514664
128. Liu, Jikai; Wang, Weiqiang; Li, Jun; Mustafa, Ghulam; Su, Xiangxiang; Nian, Ying; Ma, Qiang; Zhen, Fengxian; Wang, Wenhui; Li, Xinwei. UAV Remote Sensing Technology for Wheat Growth Monitoring in Precision Agriculture: Comparison of Data Quality and Growth Parameter Inversion. *Agronomy*, 2025. https://doi.org/10.3390/agronomy15010159
129. Liu, Min; Duan, Pengfei; Liu, Pengfei; Mei, Wanman; Wang, Dongliang; Dong, Lifeng; Wuepper, David. Quantifying greenhouse gas emissions from livestock in pastoral areas using unmanned aerial vehicles and assessing emission reduction strategies. *Smart Agricultural Technology*, 2026. https://doi.org/10.1016/j.atech.2026.102289
130. Los, S.; Mücher, C.A.; Kramer, H.; Franke, G.J.; Kamphuis, C. Estimating body dimensions and weight of cattle on pasture with 3D models from UAV imagery. *Smart Agricultural Technology*, 2023. https://doi.org/10.1016/j.atech.2022.100167
131. López, Alfonso; Ogayar, Carlos J.; Feito, Francisco R.; Sousa, Joaquim J. Classification of Grapevine Varieties Using UAV Hyperspectral Imaging. *Remote Sensing*, 2024. https://doi.org/10.3390/rs16122103
132. Lukas, Vojtěch; Huňady, Igor; Kintl, Antonín; Mezera, Jiří; Hammerschmiedt, Tereza; Sobotková, Julie; Brtnický, Martin; Elbl, Jakub. Using UAV to Identify the Optimal Vegetation Index for Yield Prediction of Oil Seed Rape (Brassica napus L.) at the Flowering Stage. *Remote Sensing*, 2022. https://doi.org/10.3390/rs14194953
133. Luo, Wei; Zhang, Guoqing; Shao, Quanqin; Zhao, Yongxiang; Wang, Dongliang; Zhang, Xiongyi; Liu, Ke; Li, Xiaoliang; Liu, Jiandong; Wang, Penggang; Li, Lin; Wang, Guanwu; Wang, Fulong; Yu, Zhongde. An efficient visual servo tracker for herd monitoring by UAV. *Scientific Reports*, 2024. https://doi.org/10.1038/s41598-024-60445-4
134. Machidon, Alina L.; Krašovec, Andraž; Pejović, Veljko; Latini, Daniele; Sasidharan, Sarathchandrakumar T.; Del Frate, Fabio; Machidon, Octavian M. A Low-Cost UAV System and Dataset for Real-Time Weed Detection in Salad Crops. *Electronics*, 2025. https://doi.org/10.3390/electronics14204082
135. Mansur, Hasib; Gadhwal, Manoj; Abon, John Eric; Flippo, Daniel. Mapping for Autonomous Navigation of Agricultural Robots Through Crop Rows Using UAV. *Agriculture*, 2025. https://doi.org/10.3390/agriculture15080882
136. Mayer, Martin; Furuhovde, Erlend; Nordli, Kristoffer; Myriam Ausilio, Giorgia; Wabakken, Petter; Eriksen, Ane; Evans, Alina L.; Mathisen, Karen Marie; Zimmermann, Barbara. Monitoring GPS‐collared moose by ground versus drone approaches: efficiency and disturbance effects. *Wildlife Biology*, 2024. https://doi.org/10.1002/wlb3.01213
137. Mücher, C. A.; Los, S.; Franke, G. J.; Kamphuis, C. Detection, identification and posture recognition of cattle with satellites, aerial photography and UAVs using deep learning techniques. *International Journal of Remote Sensing*, 2022. https://doi.org/10.1080/01431161.2022.2051634
138. Meiyan, Shu; Mengyuan, Shen; Qizhou, Dong; Xiaohong, Yang; Baoguo, Li; Yuntao, Ma. Estimating the maize above-ground biomass by constructing the tridimensional concept model based on UAV-based digital and multi-spectral images. *Field Crops Research*, 2022. https://doi.org/10.1016/j.fcr.2022.108491
139. Meng, Yanhua; Zhong, Wanqiang; Liu, Cunjia; Su, Jinya; Su, Jiyuan; Lan, Yubin; Wang, Zhiguo; Wang, Meimei. UAV spraying on citrus crop: impact of tank-mix adjuvant on the contact angle and droplet distribution. *PeerJ*, 2022. https://doi.org/10.7717/peerj.13064
140. Menshchikov, Alexander; Shadrin, Dmitrii; Prutyanov, Viktor; Lopatkin, Daniil; Sosnin, Sergey; Tsykunov, Evgeny; Iakovlev, Evgeny; Somov, Andrey. Real-Time Detection of Hogweed: UAV Platform Empowered by Deep Learning. *IEEE Transactions on Computers*, 2021. https://doi.org/10.1109/tc.2021.3059819
141. Meron, Moshe; Peres, Moti; Levin-Orlov, Valerie; Shoshani, Gil; Marchaim, Uri; Chen, Assaf. Irrigation uniformity assessment with high-resolution aerial sensors. *International Journal of Applied Earth Observation and Geoinformation*, 2025. https://doi.org/10.1016/j.jag.2025.104446
142. Mishra, Shailendra. Internet of things enabled deep learning methods using unmanned aerial vehicles enabled integrated farm management. *Heliyon*, 2023. https://doi.org/10.1016/j.heliyon.2023.e18659
143. Molins, Mireia; Calderone, Giulio; Giron, Luis; Hodder, Abby; Bryan, Dervan D.S.L; Martins, Leoni F.; Casella, Enrico. Applied Research Note: Evaluating the effects of drone presence on the behavior of tom turkey poults. *Journal of Applied Poultry Research*, 2026. https://doi.org/10.1016/j.japr.2026.100754
144. Moresi, Federico Valerio; Cirigliano, Pasquale; Rengo, Andrea; Brunori, Elena; Biasi, Rita; Scarascia Mugnozza, Giuseppe; Maesano, Mauro. Monitoring Abiotic Stressors in Rainfed Vineyards Involves Combining UAV and Field Monitoring Techniques to Enhance Precision Management. *Remote Sensing*, 2025. https://doi.org/10.3390/rs17050803
145. Mukhamediev, Ravil I.; Yakunin, Kirill; Aubakirov, Margulan; Assanov, Ilyas; Kuchin, Yan; Symagulov, Adilkhan; Levashenko, Vitaly; Zaitseva, Elena; Sokolov, Dmitry; Amirgaliyev, Yedilkhan. Coverage Path Planning Optimization of Heterogeneous UAVs Group for Precision Agriculture. *IEEE Access*, 2023. https://doi.org/10.1109/access.2023.3235207
146. Naidu, T. Yugendhar; Deekshitha, V.; Babu, V. Venkatesh; Krishna, Y. Sai; Balaji, V.; Jabbar, M.A. Integrating Multipurpose Payloads for Agricultural Advancement. *2025 International Conference on Computing Technologies & Data Communication (ICCTDC)*, 2025. https://doi.org/10.1109/icctdc64446.2025.11158891
147. Nasir, Muhammad Fahad; Rehman, Mobeen Ur; Hussain, Irfan. Vision-language models for zero-shot weed detection and visual reasoning in UAV-based precision agriculture. *Frontiers in Plant Science*, 2026. https://doi.org/10.3389/fpls.2025.1735096
148. Nazzari, Alessandro; Rubinacci, Roberto; Invernizzi, Davide. A modular multi-UAV system for precision agriculture applications. *IFAC-PapersOnLine*, 2025. https://doi.org/10.1016/j.ifacol.2025.11.812
149. Nguyen, Khanh-Van; Nguyen, Chi-Hieu; Do, Tien Van; Rotter, Csaba. Efficient Multi-UAV Assisted Data Gathering Schemes for Maximizing the Operation Time of Wireless Sensor Networks in Precision Farming. *IEEE Transactions on Industrial Informatics*, 2023. https://doi.org/10.1109/tii.2023.3248616
150. Nguyen, Dac Dang Khoa; Paul, Gavin; Alempijevic, Alen. Decentralized multi-phase formation control for cattle herding. *2024 IEEE International Conference on Robotics and Automation (ICRA)*, 2024. https://doi.org/10.1109/icra57147.2024.10611069
151. Okada, Mashiro; Barras, Clément; Toda, Yusuke; Hamazaki, Kosuke; Ohmori, Yoshihiro; Yamasaki, Yuji; Takahashi, Hirokazu; Takanashi, Hideki; Tsuda, Mai; Hirai, Masami Yokota; Tsujimoto, Hisashi; Kaga, Akito; Nakazono, Mikio; Fujiwara, Toru; Iwata, Hiroyoshi. High-Throughput Phenotyping of Soybean Biomass: Conventional Trait Estimation and Novel Latent Feature Extraction Using UAV Remote Sensing and Deep Learning Models. *Plant Phenomics*, 2024. https://doi.org/10.34133/plantphenomics.0244
152. Orioli, Guilherme Felipe; Barcelos, Jardel Perrud; Bastos, Kécia Martins; Inagaki, Felipe Minoru de Oliveira; Silveira, Robson Mateus Freitas; Nascimento, Sheila Tavares. Integrating drone imaging into behavioral monitoring of feedlot cattle. *Frontiers in Animal Science*, 2026. https://doi.org/10.3389/fanim.2026.1810888
153. Ortega, Julio César Úbeda; Rodríguez-Molina, Jesús; Martínez-Núñez, Margarita; Garbajosa, Juan. A Proposal for Decentralized and Secured Data Collection from Unmanned Aerial Vehicles in Livestock Monitoring with Blockchain and IPFS. *Applied Sciences*, 2022. https://doi.org/10.3390/app13010471
154. Pakeman, Robin J.; Bienkowski, Damian; Fielding, Debbie A.; Thiel, Andre; Evans, Darren M. Assessing the impacts of livestock grazing on upland bird breeding territories using drone surveys. *Journal of Avian Biology*, 2025. https://doi.org/10.1111/jav.03356
155. Panjaitan, Seno Darmawan; Dewi, Yohana Sutiknyawati Kusuma; Hendri, Muhammad Irfani; Wicaksono, Romario Aldrian; Priyatman, Hendro. A Drone Technology Implementation Approach to Conventional Paddy Fields Application. *IEEE Access*, 2022. https://doi.org/10.1109/access.2022.3221188
156. Pádua, Luís; Castro, João P.; Castro, José; Sousa, Joaquim J.; Castro, Marina. Assessing the Impact of Clearing and Grazing on Fuel Management in a Mediterranean Oak Forest through Unmanned Aerial Vehicle Multispectral Data. *Drones*, 2024. https://doi.org/10.3390/drones8080364
157. Pádua, Luís; Marques, Pedro; Dinis, Lia-Tânia; Moutinho-Pereira, José; Sousa, Joaquim J.; Morais, Raul; Peres, Emanuel. Detection of Leak Areas in Vineyard Irrigation Systems Using UAV-Based Data. *Drones*, 2024. https://doi.org/10.3390/drones8050187
158. Peng, Hongxing; Li, Zhenxing; Zou, Xiangjun; Wang, Hongjun; Xiong, Juntao. Research on litchi image detection in orchard using UAV based on improved YOLOv5. *Expert Systems with Applications*, 2025. https://doi.org/10.1016/j.eswa.2024.125828
159. Pierdicca, Luca; Ognibene, Dimitri; Trianni, Vito. Multi-UAV active sensing for precision agriculture via Bayesian fusion. *2024 IEEE 20th International Conference on Automation Science and Engineering (CASE)*, 2024. https://doi.org/10.1109/case59546.2024.10711773
160. Qin, Weicai; Chen, Panyang; Wang, Baokun. Productivity model and experiment of field crop spraying by plant protection unmanned aircraft. *Frontiers in Plant Science*, 2023. https://doi.org/10.3389/fpls.2023.1168228
161. Qin, Yuan; Li, Cunjun; Wang, Chaoting; Fu, Maodong; Pan, Chanling; Chen, Ruibo. Multiple unmanned aerial vehicles task allocation algorithm for agricultural scenarios based on improved non-dominated sorting genetic algorithm II. *Smart Agricultural Technology*, 2026. https://doi.org/10.1016/j.atech.2025.101700
162. Qu, Tengteng; Li, Yaoyu; Zhao, Qixin; Yin, Yunzhen; Wang, Yuzhi; Li, Fuzhong; Zhang, Wuping. Drone-Based Multispectral Remote Sensing Inversion for Typical Crop Soil Moisture under Dry Farming Conditions. *Agriculture*, 2024. https://doi.org/10.3390/agriculture14030484
163. R, Praneeth; A, Arjun V; P, Sneha; B, Rajesh C. Precision Data Collection for Enhanced Agricultural and Environmental Monitoring Using LoRa Communication. *2025 7th International Conference on Energy, Power and Environment (ICEPE)*, 2025. https://doi.org/10.1109/icepe65965.2025.11139591
164. Rai, Nitin; Zhang, Yu; Villamil, Maria; Howatt, Kirk; Ostlie, Michael; Sun, Xin. Agricultural weed identification in images and videos by integrating optimized deep learning architecture on an edge computing technology. *Computers and Electronics in Agriculture*, 2024. https://doi.org/10.1016/j.compag.2023.108442
165. Ramteke, Shefali Vinod; Varadwaj, Pritish Kumar; Tiwari, Vineet. Optimizing UAV Spraying for Sustainable Agriculture: A Life Cycle and Efficiency Analysis in India. *Sustainability*, 2025. https://doi.org/10.3390/su17136211
166. Ranđelović, Predrag; Đorđević, Vuk; Miladinović, Jegor; Prodanović, Slaven; Ćeran, Marina; Vollmann, Johann. High-throughput phenotyping for non-destructive estimation of soybean fresh biomass using a machine learning model and temporal UAV data. *Plant Methods*, 2023. https://doi.org/10.1186/s13007-023-01054-6
167. Raptis, Emmanuel K.; Krestenitis, Marios; Egglezos, Konstantinos; Kypris, Orfeas; Ioannidis, Konstantinos; Doitsidis, Lefteris; Kapoutsis, Athanasios Ch.; Vrochidis, Stefanos; Kompatsiaris, Ioannis; Kosmatopoulos, Elias B. End-to-end Precision Agriculture UAV-Based Functionalities Tailored to Field Characteristics. *Journal of Intelligent & Robotic Systems*, 2023. https://doi.org/10.1007/s10846-022-01761-7
168. Rayner, KL; Wilson, ME. Distance examination of livestock with drones ‐ an effective method for assessing health and welfare. *Australian Veterinary Journal*, 2024. https://doi.org/10.1111/avj.13326
169. Rietz, Janine; van Beeck Calkoen, Suzanne T. S.; Ferry, Nicolas; Schlüter, Jens; Wehner, Helena; Schindlatz, Karl-Heinz; Lackner, Tomáš; von Hoermann, Christian; Conraths, Franz J.; Müller, Jörg; Heurich, Marco. Drone-Based Thermal Imaging in the Detection of Wildlife Carcasses and Disease Management. *Transboundary and Emerging Diseases*, 2023. https://doi.org/10.1155/2023/5517000
170. Rocha, Maria Angélica Damasceno; Monteiro, Frederico Ozanan Barros. Use of drones to study the behavior of buffaloes in a production system in the Eastern Amazon. *Brazilian Journal of Veterinary Medicine*, 2025. https://doi.org/10.29374/2527-2179.bjvm003325
171. Rodene, Eric; Xu, Gen; Palali Delen, Semra; Zhao, Xia; Smith, Christine; Ge, Yufeng; Schnable, James; Yang, Jinliang. A UAV‐based high‐throughput phenotyping approach to assess time‐series nitrogen responses and identify trait‐associated genetic components in maize. *The Plant Phenome Journal*, 2022. https://doi.org/10.1002/ppj2.20030
172. Sadiq, Bashir Olaniyi; Buhari, Mohammed Dahiru; Danjuma, Yale Ibrahim; Zakariyya, Olayinka Sikiru; Shuaibu, Aliyu Nuhu. High-tech herding: Exploring the use of IoT and UAV networks for improved health surveillance in dairy farm system. *Scientific African*, 2024. https://doi.org/10.1016/j.sciaf.2024.e02266
173. Sadiq, Bashir Olaniyi; Al-Mutairi, Motirh; Sha’aban, Yusuf Abubakar; Bouchekara, Houssem Rafik El-Hana; Almutairi, Khalid. Sky and wire: A UAV-BPL synchronization algorithm for information exchange in herding operations. *PLOS One*, 2025. https://doi.org/10.1371/journal.pone.0334888
174. Safaeinejad, Mojtaba; Ghasemi-Nejad-Raeini, Mahmoud; Taki, Morteza. Reducing energy and environmental footprint in agriculture: A study on drone spraying vs. conventional methods. *PLOS One*, 2025. https://doi.org/10.1371/journal.pone.0323779
175. Sankararao, Adduru U G; Rajalakshmi, P.; Kaliamoorthy, Sivasakthi; Choudhary, Sunitha. Water Stress Detection in Pearl Millet Canopy with Selected Wavebands using UAV Based Hyperspectral Imaging and Machine Learning. *2022 IEEE Sensors Applications Symposium (SAS)*, 2022. https://doi.org/10.1109/sas54819.2022.9881337
176. Sankararao, Adduru U. G.; Rajalakshmi, P.; Choudhary, Sunita. Machine Learning-Based Ensemble Band Selection for Early Water Stress Identification in Groundnut Canopy Using UAV-Based Hyperspectral Imaging. *IEEE Geoscience and Remote Sensing Letters*, 2023. https://doi.org/10.1109/lgrs.2023.3284675
177. Shafiee, Sahameh; Mroz, Tomasz; Burud, Ingunn; Lillemo, Morten. Evaluation of UAV multispectral cameras for yield and biomass prediction in wheat under different sun elevation angles and phenological stages. *Computers and Electronics in Agriculture*, 2023. https://doi.org/10.1016/j.compag.2023.107874
178. Shammi, Sadia Alam; Huang, Yanbo; Feng, Gary; Tewolde, Haile; Zhang, Xin; Jenkins, Johnie; Shankle, Mark. Application of UAV Multispectral Imaging to Monitor Soybean Growth with Yield Prediction through Machine Learning. *Agronomy*, 2024. https://doi.org/10.3390/agronomy14040672
179. Sharma, Vikas; Honkavaara, Eija; Hayden, Matthew; Kant, Surya. UAV remote sensing phenotyping of wheat collection for response to water stress and yield prediction using machine learning. *Plant Stress*, 2024. https://doi.org/10.1016/j.stress.2024.100464
180. Shen, Yulin; Mercatoris, Benoît; Cao, Zhen; Kwan, Paul; Guo, Leifeng; Yao, Hongxun; Cheng, Qian. Improving Wheat Yield Prediction Accuracy Using LSTM-RF Framework Based on UAV Thermal Infrared and Multispectral Imagery. *Agriculture*, 2022. https://doi.org/10.3390/agriculture12060892
181. Shen, Yutao; Lu, Xuqi; Lyu, Mengqi; Zhou, Hongyu; Guan, Wenxuan; Jiang, Lixi; He, Yuhong; Cen, Haiyan. High-throughput phenotyping of individual plant height in an oilseed rape population based on Mask-RCNN and UAV images. *Precision Agriculture*, 2024. https://doi.org/10.1007/s11119-023-10095-9
182. Shen, Peng; Wang, Fulong; Luo, Wei; Zhao, Yongxiang; Li, Lin; Zhang, Guoqing; Zhu, Yuchen. Based on improved joint detection and tracking of UAV for multi-target detection of livestock. *Heliyon*, 2024. https://doi.org/10.1016/j.heliyon.2024.e38316
183. Shi, Haibin; Wang, Zikang. Research on Strategies of Herding a Flock of Birds by Multiple UAVs. *2022 34th Chinese Control and Decision Conference (CCDC)*, 2022. https://doi.org/10.1109/ccdc55256.2022.10034366
184. Shokati, Hadi; Mashal, Mahmoud; Noroozi, Aliakbar; Abkar, Ali Akbar; Mirzaei, Saham; Mohammadi-Doqozloo, Zahra; Taghizadeh-Mehrjardi, Ruhollah; Khosravani, Pegah; Nabiollahi, Kamal; Scholten, Thomas. Random Forest-Based Soil Moisture Estimation Using Sentinel-2, Landsat-8/9, and UAV-Based Hyperspectral Data. *Remote Sensing*, 2024. https://doi.org/10.3390/rs16111962
185. Singh, Edward; Pratap, Aashutosh; Mehta, Utkal; Azid, Sheikh Izzal. Smart Agriculture Drone for Crop Spraying Using Image-Processing and Machine Learning Techniques: Experimental Validation. *IoT*, 2024. https://doi.org/10.3390/iot5020013
186. Betti Sorbelli, Francesco; Coro, Federico; Das, Sajal K.; Di Bella, Emanuele; Maistrello, Lara; Palazzetti, Lorenzo; Pinotti, Cristina M. A Drone-based Application for Scouting Halyomorpha halys Bugs in Orchards with Multifunctional Nets. *2022 IEEE International Conference on Pervasive Computing and Communications Workshops and other Affiliated Events (PerCom Workshops)*, 2022. https://doi.org/10.1109/percomworkshops53856.2022.9767309
187. Betti Sorbelli, Francesco; Palazzetti, Lorenzo; Pinotti, Cristina M. Preliminary Results for Halyomorpha halys Monitoring Relying on a Custom Dataset. *2023 IEEE International Workshop on Metrology for Agriculture and Forestry (MetroAgriFor)*, 2023. https://doi.org/10.1109/metroagrifor58484.2023.10424403
188. Spizzirri, U. G.; Notarnicola, B.; Molfetta, M. De; Renzulli, P. A.; Astuto, F.; Lovarelli, D.; Zoli, M.; Fosco, D. Direct measurement of methane emissions in cattle breeds by using UAV monitoring systems to improve data quality in LCA. *The International Journal of Life Cycle Assessment*, 2026. https://doi.org/10.1007/s11367-026-02620-5
189. Stache, Felix; Westheider, Jonas; Magistri, Federico; Stachniss, Cyrill; Popović, Marija. Adaptive path planning for UAVs for multi-resolution semantic segmentation. *Robotics and Autonomous Systems*, 2023. https://doi.org/10.1016/j.robot.2022.104288
190. Subeesh, A.; Prakash Kumar, Satya; Kumar Chakraborty, Subir; Upendar, Konga; Singh Chandel, Narendra; Jat, Dilip; Dubey, Kumkum; Modi, Rajesh U.; Mazhar Khan, Mohammad. UAV imagery coupled deep learning approach for the development of an adaptive in-house web-based application for yield estimation in citrus orchard. *Measurement*, 2024. https://doi.org/10.1016/j.measurement.2024.114786
191. Sun, Xuguang; Zhang, Baoyuan; Dai, Menglei; Jing, Cuijiao; Ma, Kai; Tang, Boyi; Li, Kejiang; Dang, Hongkai; Gu, Limin; Zhen, Wenchao; Gu, Xiaohe. Accurate irrigation decision-making of winter wheat at the filling stage based on UAV hyperspectral inversion of leaf water content. *Agricultural Water Management*, 2024. https://doi.org/10.1016/j.agwat.2024.109171
192. T., Barathkumar; J, Cyril Joshua; H, Diwan Mohamed; M, Harish. Fuzzy Logic-Based Dynamic Prioritization for UAV Wireless Charging Systems in Agriculture. *2024 International Conference on IoT Based Control Networks and Intelligent Systems (ICICNIS)*, 2024. https://doi.org/10.1109/icicnis64247.2024.10823327
193. Tian, Xinyu; Afrin, Mahbuba; Mistry, Sajib; Mahmud, Redowan; Krishna, Aneesh; Li, Yan. MURE: Multi-layer real-time livestock management architecture with unmanned aerial vehicles using deep reinforcement learning. *Future Generation Computer Systems*, 2024. https://doi.org/10.1016/j.future.2024.07.038
194. Tulu, Boaz B.; Teshome, Fitsum; Ampatzidis, Yiannis; Hailegnaw, Niguss Solomon; Bayabil, Haimanote K. AgriSenAI: Automating UAV thermal and multispectral image processing for precision agriculture. *SoftwareX*, 2025. https://doi.org/10.1016/j.softx.2025.102083
195. Turnip, Arjon; Taufik, Mohammad. Design of intelligent sprayer control for an autonomous farming drone using a multiclass support vector machine. *Open Agriculture*, 2024. https://doi.org/10.1515/opag-2022-0375
196. Umeda, Shotaro; Yoshikawa, Naoki; Seo, Yuna. Cost and Workload Assessment of Agricultural Drone Sprayer: A Case Study of Rice Production in Japan. *Sustainability*, 2022. https://doi.org/10.3390/su141710850
197. Vaghalandari, Nasrin Ghadami; Kołakowska, Agata; Grundig, Christoph; Dongchen, Li; Wiszniewski, Bogdan; Daniel, Kai; Obermaisser, Roman. Performance Evaluation of Nomadic Data Collection with a UAV-LoRa System. *2025 21st International Conference on Distributed Computing in Smart Systems and the Internet of Things (DCOSS-IoT)*, 2025. https://doi.org/10.1109/dcoss-iot65416.2025.00143
198. Vahidi, Milad; Shafian, Sanaz; Frame, William Hunter. Multi-depth soil moisture estimation via 1D convolutional neural networks from drone-mounted ground penetrating Radar data. *Computers and Electronics in Agriculture*, 2025. https://doi.org/10.1016/j.compag.2025.110104
199. Vallejos-Fernández, Luis; Alvarez-García, Wuesley; Abanto-Urbina, Maycol; Gutiérrez-Arce, Felipe; Tapia-Acosta, Eduardo; Pizarro, Samuel; Ciprian, Cesar; Naupari, Javier. Monitoring ryegrass-clover grasslands with multi-spectral UAV imagery will improve the sustainability of small-and medium-sized livestock farmers in the northern Peruvian highlands. *Sustainable Environment*, 2026. https://doi.org/10.1080/27658511.2026.2623335
200. Vannini, Veronica; de Moura Souza, Gustavo; Toledo, Claudio Fabiano Motta. Harpia: A hybrid system for agricultural UAV missions. *Smart Agricultural Technology*, 2023. https://doi.org/10.1016/j.atech.2023.100191
201. Vishwakarma, Sumit Kumar; Bhattarai, Benu; Kothari, Kritika; Pandey, Ashish. Mapping crop water productivity of rice across diverse irrigation and fertilizer rates using field experiment and UAV-based multispectral data. *Remote Sensing Applications: Society and Environment*, 2025. https://doi.org/10.1016/j.rsase.2025.101456
202. Vélez, Sergio; Ariza-Sentís, Mar; Valente, João. EscaYard: Precision viticulture multimodal dataset of vineyards affected by Esca disease consisting of geotagged smartphone images, phytosanitary status, UAV 3D point clouds and Orthomosaics. *Data in Brief*, 2024. https://doi.org/10.1016/j.dib.2024.110497
203. Vélez, Sergio; Ariza-Sentís, Mar; Triviño, Mario; Cob-Parro, Antonio Carlos; Mila, Miquel; Valente, João. Framework for smartphone-based grape detection and vineyard management using UAV-trained AI. *Heliyon*, 2025. https://doi.org/10.1016/j.heliyon.2025.e42525
204. Wang, Hao; Zhang, Xihai; Meng, Xiangyu; Song, Weixian; Chen, Zerui. Electronic Sheepdog: A Novel Method in With UAV-Assisted Wearable Grazing Monitoring. *IEEE Internet of Things Journal*, 2023. https://doi.org/10.1109/jiot.2023.3267108
205. Wang, Yuhang; Ma, Lingling; Wang, Qi; Wang, Ning; Wang, Dongliang; Wang, Xinhong; Zheng, Qingchuan; Hou, Xiaoxin; Ouyang, Guangzhou. A Lightweight and High-Accuracy Deep Learning Method for Grassland Grazing Livestock Detection Using UAV Imagery. *Remote Sensing*, 2023. https://doi.org/10.3390/rs15061593
206. Wang, Zhongkuan; Wen, Sheng; Lan, Yubin; Liu, Yue; Dong, Yingying. Variable-rate spray system for unmanned aerial applications using lag compensation algorithm and pulse width modulation spray technology. *Journal of Agricultural Engineering*, 2023. https://doi.org/10.4081/jae.2023.1547
207. Wang, Yaowu; Mücher, Sander; Wang, Wensheng; Kooistra, Lammert. Automated retrieval of cattle body measurements from unmanned aerial vehicle-based LiDAR point clouds. *Computers and Electronics in Agriculture*, 2024. https://doi.org/10.1016/j.compag.2024.109521
208. Wang, Pingan; Saiful Hanif, Adhitya; Yu, Seung-Hwa; Lee, Chun-Gu; Ho Kang, Yeong; Lee, Dae-Hyun; Han, Xiongzhe. Development of an autonomous drone spraying control system based on the coefficient of variation of spray distribution. *Computers and Electronics in Agriculture*, 2024. https://doi.org/10.1016/j.compag.2024.109529
209. Wang, Yuxiang; Kootstra, Gert; Yang, Zengling; Khan, Haris Ahmad. UAV multispectral remote sensing for agriculture: A comparative study of radiometric correction methods under varying illumination conditions. *Biosystems Engineering*, 2024. https://doi.org/10.1016/j.biosystemseng.2024.11.005
210. Wang, Jingjing; Lou, Yu; Wang, Wentao; Liu, Suyi; Zhang, Haohui; Hui, Xin; Wang, Yunling; Yan, Haijun; Maes, Wouter H. A robust model for diagnosing water stress of winter wheat by combining UAV multispectral and thermal remote sensing. *Agricultural Water Management*, 2024. https://doi.org/10.1016/j.agwat.2023.108616
211. Wang, Shu-Mao; Yu, Cui-Ping; Ma, Jun-Hui; Ouyang, Jia-Xue; Zhao, Zhu-Meng; Xuan, Yi-Min; Fan, Dong-Mei; Yu, Jin-Feng; Wang, Xiao-Chang; Zheng, Xin-Qiang. Tea yield estimation using UAV images and deep learning. *Industrial Crops and Products*, 2024. https://doi.org/10.1016/j.indcrop.2024.118358
212. Wang, Zhijiang; Mi, Ruxue; Liu, Haoyuan; Yi, Mengyao; Fan, Yanjie; Hu, Guangying; Liu, Zhenyu. Low-Altitude UAV-Based Recognition of Porcine Facial Expressions for Early Health Monitoring. *Animals*, 2025. https://doi.org/10.3390/ani15233426
213. Wang, Yaowu; Mücher, Sander; Wang, Wensheng; Kooistra, Lammert. Body Weight Estimation of Cattle in Standing and Lying Postures Using Point Clouds Derived from Unmanned Aerial Vehicle-Based LiDAR. *Drones*, 2025. https://doi.org/10.3390/drones9020084
214. Wang, You; Yu, Rui; Li, Xin; Chen, Ronghao; Liu, Jiahui. Grazing regime rather than grazing intensity affect the foraging behavior of cattle. *Ecological Informatics*, 2025. https://doi.org/10.1016/j.ecoinf.2025.102996
215. Wang, Yaowu; Kooistra, Lammert; Mücher, Sander; Wang, Wensheng. Integrated unmanned aerial vehicle-based LiDAR and RGB data for individual cattle growth monitoring in precision livestock farming. *Scientific Data*, 2025. https://doi.org/10.1038/s41597-025-04783-6
216. Wang, Jingjing; Wang, Wentao; Liu, Suyi; Hui, Xin; Zhang, Haohui; Yan, Haijun; Maes, Wouter H. UAV-Based Multiple Sensors for Enhanced Data Fusion and Nitrogen Monitoring in Winter Wheat Across Growth Seasons. *Remote Sensing*, 2025. https://doi.org/10.3390/rs17030498
217. Wei, Xu; Zhang, Zhixun; Li, Huifen; Wu, Han; Lv, Jia; Wu, Longmei; Zhou, Meizhen; Li, Jiyu. Influences of wind vortex intensity of rotor UAV on rice morphology and yield. *Precision Agriculture*, 2023. https://doi.org/10.1007/s11119-023-10017-9
218. Wongsuk, Supakorn; Qi, Peng; Wang, Changling; Zeng, Aijun; Sun, Fuyu; Yu, Fengquan; Zhao, Xu; Xiongkui, He. Spray performance and control efficacy against pests in paddy rice by UAV ‐based pesticide application: effects of atomization, UAV configuration and flight velocity. *Pest Management Science*, 2024. https://doi.org/10.1002/ps.7942
219. Xiao, Xiongwu; Qu, Wenhu; Xia, Gui-Song; Xu, Miaozhong; Shao, Zhenfeng; Gong, Jianya; Li, Deren. A novel real-time matching and pose reconstruction method for low-overlap agricultural UAV images with repetitive textures. *ISPRS Journal of Photogrammetry and Remote Sensing*, 2025. https://doi.org/10.1016/j.isprsjprs.2025.05.009
220. Xiu, Yangjing; Ge, Jing; Guo, Rui; Fu, Shuai; He, Jinsheng; Liang, Tiangang; Feng, Qisheng; Chen, Jigui; Guo, Zhiying. Fine Mapping and Dynamic Analysis of Grassland–Livestock Balance in Alpine Grassland From 2019 to 2022 Based on RAV-Satellite Spectral Fusion and Statistical Data Spatialization. *IEEE Transactions on Geoscience and Remote Sensing*, 2025. https://doi.org/10.1109/tgrs.2025.3541269
221. Xu, Hang; Yi, Lili; Li, Chuanyong; Sun, Yuemei; Hou, Liangchen; Bai, Jingbo; Kong, Fanxia; Han, Xin; Lan, Yubin. Design and Experiment of Ecological Plant Protection UAV Based on Ozonated Water Spraying. *Drones*, 2023. https://doi.org/10.3390/drones7050291
222. Xu, Sizhe; Xu, Xingang; Zhu, Qingzhen; Meng, Yang; Yang, Guijun; Feng, Haikuan; Yang, Min; Zhu, Qilei; Xue, Hanyu; Wang, Binbin. Monitoring leaf nitrogen content in rice based on information fusion of multi-sensor imagery from UAV. *Precision Agriculture*, 2023. https://doi.org/10.1007/s11119-023-10042-8
223. Yan, Jianglong; Tetila, Everton C.; Zhao, Liang; Gonçalves, Rian C.; Castanheiro, Letícia F.; Valem, Lucas P.; Barbedo, Jayme G.A. Deep learning-based UAV framework for automated morphological and growth analysis of feedlot cattle. *Computers and Electronics in Agriculture*, 2026. https://doi.org/10.1016/j.compag.2026.111559
224. Yang, Yandong; Li, Qing; Mu, Yue; Li, Haitao; Wang, Hengtong; Ninomiya, Seishi; Jiang, Dong. UAV-Assisted Dynamic Monitoring of Wheat Uniformity toward Yield and Biomass Estimation. *Plant Phenomics*, 2024. https://doi.org/10.34133/plantphenomics.0191
225. Yang, Doee; Akdeniz, Neslihan; Karthikeyan, K. G. Direct Air Emission Measurements from Livestock Pastures Using an Unmanned Aerial Vehicle-Based Air Sampling System. *Remote Sensing*, 2025. https://doi.org/10.3390/rs17173059
226. Yang, Shenghui; Zhai, Shuyuan; Yu, Xiangye; Liu, Weihong; Zheng, Yongjun; Zhao, Hangxing; Feng, Han; Wang, Haoyu; Xu, Wenbo. Synchronous Spray Effect Based on Dual Plant-Protection UAV Collaboration in Corn Fields. *Agronomy*, 2026. https://doi.org/10.3390/agronomy16030292
227. Ye, Nan; Walker, Jeffrey P.; Gao, Ying; PopStefanija, Ivan; Hills, James. Comparison Between Thermal-Optical and L-Band Passive Microwave Soil Moisture Remote Sensing at Farm Scales: Towards UAV-Based Near-Surface Soil Moisture Mapping. *IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing*, 2024. https://doi.org/10.1109/jstars.2023.3329015
228. Yin, Caixia; Lv, Xin; Zhang, Lifu; Ma, Lulu; Wang, Huihan; Zhang, Linshan; Zhang, Ze. Hyperspectral UAV Images at Different Altitudes for Monitoring the Leaf Nitrogen Content in Cotton Crops. *Remote Sensing*, 2022. https://doi.org/10.3390/rs14112576
229. Zhang, Yu; Han, Wenting; Zhang, Huihui; Niu, Xiaotao; Shao, Guomin. Evaluating soil moisture content under maize coverage using UAV multimodal data by machine learning algorithms. *Journal of Hydrology*, 2023. https://doi.org/10.1016/j.jhydrol.2023.129086
230. Zhang, Zhihong; Yuan, Shuo; Lai, Qinghui; Zeng, Ronghao; Zhang, Jingkun; Shen, Siyu. Precision Variable-rate Control System for Mini-UAV-based Pesticide Application. *Journal of Physics: Conference Series*, 2023. https://doi.org/10.1088/1742-6596/2557/1/012006
231. Zhang, Guoqing; Liu, Jiandong; Luo, Wei; Zhao, Yongxiang; Tang, Ruiyin; Mei, Keyu; Wang, Penggang. A Shortest Distance Priority UAV Path Planning Algorithm for Precision Agriculture. *Sensors*, 2024. https://doi.org/10.3390/s24237514
232. Zhang, Jingyao; Chen, Haihua; Dai, Feng; Wang, Yancong; Li, Heyang; Zhang, Yucheng. A Fast Multi-UAV Assistance Positioning Architecture for Large-Scale Farming Operations. *IEEE Internet of Things Journal*, 2025. https://doi.org/10.1109/jiot.2025.3584091
233. Zhang, Xin; Zhang, Lina; Yang, Lu; Yang, Fan; Zhang, Jue; Jiang, Xinhua; Jiao, Licheng; Gong, Maoguo. An automated dynamic adaptive tracking and counting method for grazing sheep based on UAV imagery and YOLO11-OBB. *Computers and Electronics in Agriculture*, 2026. https://doi.org/10.1016/j.compag.2026.112086
234. Zhang, Hua; Kuhn, Lena; Xiong, Hang; Sun, Zhanli. Farmers’ preferences for agricultural drone services under uncertainty: A choice experiment in Hubei, China. *Journal of Integrative Agriculture*, 2026. https://doi.org/10.1016/j.jia.2025.12.066
235. Zhang, Weixing; Jiang, Minlan; Gao, Shupeng; Gao, Weifeng; Al-qaness, Mohammed A.A. Real-time soybean pest detection system integrating UAV and Jetson based on improved YOLO. *Neural Networks*, 2026. https://doi.org/10.1016/j.neunet.2026.109051
236. Zhao, Lei; Um, Dugan; Nowka, Kevin; Landivar-Scott, Jose Luis; Landivar, Juan; Bhandari, Mahendra. Cotton yield prediction utilizing unmanned aerial vehicles (UAV) and Bayesian neural networks. *Computers and Electronics in Agriculture*, 2024. https://doi.org/10.1016/j.compag.2024.109415
237. Zhao, He; Wang, Jingjing; Guo, Jiali; Hui, Xin; Wang, Yunling; Cai, Dongyu; Yan, Haijun. Detecting Water Stress in Winter Wheat Based on Multifeature Fusion from UAV Remote Sensing and Stacking Ensemble Learning Method. *Remote Sensing*, 2024. https://doi.org/10.3390/rs16214100
238. Zhou, Hongkui; Huang, Fudeng; Lou, Weidong; Gu, Qing; Ye, Ziran; Hu, Hao; Zhang, Xiaobin. Yield prediction through UAV-based multispectral imaging and deep learning in rice breeding trials. *Agricultural Systems*, 2025. https://doi.org/10.1016/j.agsy.2024.104214
239. Zhou, Dianyi. Endurance Optimization and Charging Path Planning for Agricultural UAV Swarms Based on an Energy-Constrained Model. *2026 8th International Conference on Information Science, Electrical and Automation Engineering (ISEAE)*, 2026. https://doi.org/10.1109/iseae69422.2026.11544307
240. Zhu, Xiaojing; Liu, Xin; Wu, Qian; Liu, Mengshi; Hu, Xueli; Deng, Hui; Zhang, Yun; Qu, Yunfeng; Wang, Baoqi; Gou, Xiaoman; Li, Qiongge; Han, Changsheng; Tu, Junhao; Qiu, Xiaolong; Hu, Ge; Zhang, Jian; Hu, Lin; Zhou, Yun; Zhang, Zhen. Utilizing UAV-based high-throughput phenotyping and machine learning to evaluate drought resistance in wheat germplasm. *Computers and Electronics in Agriculture*, 2025. https://doi.org/10.1016/j.compag.2025.110602
241. Adam, Muhammad; Song, Jianchao; Yu, Wei; Li, Qingqing. Deep Learning Approaches for Automatic Livestock Detection in UAV Imagery: State-of-the-Art and Future Directions. *Future Internet*, 2025. https://doi.org/10.3390/fi17090431
242. Afridi, Saadia; Hlebowicz, Kasper; Cawthorne, Dylan; Lundquist, Ulrik Pagh Schultz. Unveiling the Impact of Drone Noise on Wildlife: A Crucial Research Imperative. *2024 International Conference on Unmanned Aircraft Systems (ICUAS)*, 2024. https://doi.org/10.1109/icuas60882.2024.10557094
243. Agrawal, Juhi; Arafat, Muhammad Yeasir. Transforming Farming: A Review of AI-Powered UAV Technologies in Precision Agriculture. *Drones*, 2024. https://doi.org/10.3390/drones8110664
244. Anam, Iftekhar; Arafat, Naiem; Hafiz, Md Sadman; Jim, Jamin Rahman; Kabir, Md Mohsin; Mridha, M.F. A systematic review of UAV and AI integration for targeted disease detection, weed management, and pest control in precision agriculture. *Smart Agricultural Technology*, 2024. https://doi.org/10.1016/j.atech.2024.100647
245. Bernabucci, Gloria; Evangelista, Chiara; Girotti, Pedro; Viola, Paolo; Spina, Raffaello; Ronchi, Bruno; Bernabucci, Umberto; Basiricò, Loredana; Turini, Luca; Mantino, Alberto; Mele, Marcello; Primi, Riccardo. Precision livestock farming: an overview on the application in extensive systems. *Italian Journal of Animal Science*, 2025. https://doi.org/10.1080/1828051x.2025.2480821
246. Bongomin, Ocident; Lamo, Jimmy; Guina, Joshua Mugeziaubwa; Okello, Collins; Ocen, Gilbert Gilibrays; Obura, Morish; Alibu, Simon; Owino, Cynthia Awuor; Akwero, Agnes; Ojok, Samson. UAV image acquisition and processing for high‐throughput phenotyping in agricultural research and breeding programs. *The Plant Phenome Journal*, 2024. https://doi.org/10.1002/ppj2.20096
247. Borah, Sanjeet Kumar; Padhiary, Mrutyunjay; Sethi, Laxmi Narayan; Kumar, Avinash; Saikia, Pranjal. Precision Farming with Drone Sprayers: A Review of Auto Navigation and Vision-Based Optimization. *Journal of Biosystems Engineering*, 2025. https://doi.org/10.1007/s42853-025-00263-2
248. Bretas, Igor L.; Dubeux, Jose C. B.; Cruz, Priscila J. R.; Oduor, Kenneth T.; Queiroz, Luana D.; Valente, Domingos S. M.; Chizzotti, Fernanda H. M. Precision livestock farming applied to grazingland monitoring and management—A review. *Agronomy Journal*, 2024. https://doi.org/10.1002/agj2.21346
249. Cao, Yuanyang; Chen, Tao; Zhang, Zichao; Chen, Jian. An Intelligent Grazing Development Strategy for Unmanned Animal Husbandry in China. *Drones*, 2023. https://doi.org/10.3390/drones7090542
250. Caroppo, Andrea; Diraco, Giovanni; Leone, Alessandro. A Systematic Review of Available Multispectral UAV Image Datasets for Precision Agriculture Applications. *Remote Sensing*, 2026. https://doi.org/10.3390/rs18040659
251. Dong, Hao; Dong, Jiahui; Sun, Shikun; Bai, Ting; Zhao, Dongmei; Yin, Yali; Shen, Xin; Wang, Yakun; Zhang, Zhitao; Wang, Yubao. Crop water stress detection based on UAV remote sensing systems. *Agricultural Water Management*, 2024. https://doi.org/10.1016/j.agwat.2024.109059
252. Epifani, Lorenzo; Caruso, Antonio. A survey on deep learning in UAV imagery for precision agriculture and wild flora monitoring: Datasets, models and challenges. *Smart Agricultural Technology*, 2024. https://doi.org/10.1016/j.atech.2024.100625
253. Gong, Ran; Zhang, Hongyang; Li, Gang; He, Jiamin. Edge Computing-Enabled Smart Agriculture: Technical Architectures, Practical Evolution, and Bottleneck Breakthroughs. *Sensors*, 2025. https://doi.org/10.3390/s25175302
254. Liu, Xu; Chen, Steven W.; Nardari, Guilherme V.; Qu, Chao; Cladera, Fernando; Taylor, Camillo J.; Kumar, Vijay. Challenges and Opportunities for Autonomous Micro-UAVs in Precision Agriculture. *IEEE Micro*, 2022. https://doi.org/10.1109/mm.2021.3134744
255. Majumdar, Parijata; Mitra, Sanjoy; Bhattacharya, Diptendu; Bhushan, Bharat. Enhancing sustainable 5G powered agriculture 4.0 : Summary of low power connectivity, internet of UAV things, AI solutions and research trends. *Multimedia Tools and Applications*, 2024. https://doi.org/10.1007/s11042-024-19728-1
256. Merz, Mariann; Pedro, Dário; Skliros, Vasileios; Bergenhem, Carl; Himanka, Mikko; Houge, Torbjørn; Matos-Carvalho, João P.; Lundkvist, Henrik; Cürüklü, Baran; Hamrén, Rasmus; Ameri, Afshin E.; Ahlberg, Carl; Johansen, Gorm. Autonomous UAS-Based Agriculture Applications: General Overview and Relevant European Case Studies. *Drones*, 2022. https://doi.org/10.3390/drones6050128
257. Ren, Zhigang; Zheng, Han; Chen, Jian; Chen, Tao; Xie, Pengyang; Xu, Yunzhe; Deng, Jiaming; Wang, Huanzhe; Sun, Mingjiang; Jiao, Wenchi. Integrating UAV, UGV and UAV-UGV collaboration in future industrialized agriculture: Analysis, opportunities and challenges. *Computers and Electronics in Agriculture*, 2024. https://doi.org/10.1016/j.compag.2024.109631
258. Rodimov, O. A.; Naumov, I. I.; Lyashov, M. V. Robotic Thermal Imaging Systems for Animal Health Monitoring. *2026 International Conference on Industrial Engineering, Applications and Manufacturing (ICIEAM)*, 2026. https://doi.org/10.1109/icieam69213.2026.11549837
259. Rong, Zifan; Ru, Yu; Zhang, Xiao; Fang, Shuping; Zhou, Hongping; Jiang, Xuesong. Research progress on precision orchard yield estimation based on multi-source information perception sensors. *Frontiers in Plant Science*, 2026. https://doi.org/10.3389/fpls.2026.1759956
260. Saini, Puneet; Nagesh, D.S. A review of deep learning applications in weed detection: UAV and robotic approaches for precision agriculture. *European Journal of Agronomy*, 2025. https://doi.org/10.1016/j.eja.2025.127652
261. Santos, Wagner Martins dos; Martins, Lady Daiane Costa de Sousa; Bezerra, Alan Cezar; Souza, Luciana Sandra Bastos de; Jardim, Alexandre Maniçoba da Rosa Ferraz; Silva, Marcos Vinícius da; Souza, Carlos André Alves de; Silva, Thieres George Freire da. Use of Unmanned Aerial Vehicles for Monitoring Pastures and Forages in Agricultural Sciences: A Systematic Review. *Drones*, 2024. https://doi.org/10.3390/drones8100585
262. Tanaka, Takashi Sonam Tashi; Wang, Sheng; Jørgensen, Johannes Ravn; Gentili, Marco; Vidal, Armelle Zaragüeta; Mortensen, Anders Krogh; Acharya, Bharat Sharma; Beck, Brittany Deanna; Gislum, René. Review of Crop Phenotyping in Field Plot Experiments Using UAV-Mounted Sensors and Algorithms. *Drones*, 2024. https://doi.org/10.3390/drones8060212
263. Toscano, Francesco; Fiorentino, Costanza; Capece, Nicola; Erra, Ugo; Travascia, Danilo; Scopa, Antonio; Drosos, Marios; D’Antonio, Paola. Unmanned Aerial Vehicle for Precision Agriculture: A Review. *IEEE Access*, 2024. https://doi.org/10.1109/access.2024.3401018
264. Tzanidakis, Christos; Tzamaloukas, Ouranios; Simitzis, Panagiotis; Panagakis, Panagiotis. Precision Livestock Farming Applications (PLF) for Grazing Animals. *Agriculture*, 2023. https://doi.org/10.3390/agriculture13020288
265. Vera-Esmeraldas, Adrián; Pizarro-Oteíza, Sebastián; Labbé, Mariela; Rojo, Francisco; Salazar, Fernando. UAV-Based Spectral and Thermal Indices in Precision Viticulture: A Review of NDVI, NDRE, SAVI, GNDVI, and CWSI. *Agronomy*, 2025. https://doi.org/10.3390/agronomy15112569
266. Yu, Kang; Belwalkar, Anirudh; Wang, Wuhua; Hu, Yuncai; Hunegnaw, Addisu; Nurunnabi, Abdul; Ruf, Thorsten; Li, Fei; Jia, Liangliang; Kooistra, Lammert; Miao, Yuxin; Teferle, Félicia N. UAV hyperspectral remote sensing for crop nitrogen monitoring: progress, challenges, and perspectives. *Smart Agricultural Technology*, 2025. https://doi.org/10.1016/j.atech.2025.101507
267. Zhang, Shuang; Wang, Xiaorui; Lin, Hong; Dong, Yueyu; Qiang, Zhenping. A review of the application of UAV multispectral remote sensing technology in precision agriculture. *Smart Agricultural Technology*, 2025. https://doi.org/10.1016/j.atech.2025.101406
268. Zhu, Hongyan; Lin, Chengzhi; Liu, Gengqi; Wang, Dani; Qin, Shuai; Li, Anjie; Xu, Jun-Li; He, Yong. Intelligent agriculture: deep learning in UAV-based remote sensing imagery for crop diseases and pests detection. *Frontiers in Plant Science*, 2024. https://doi.org/10.3389/fpls.2024.1435016
269. Arroyo, Patricia; Herrero, José Luis; Lozano, Jesús; Montero, Pablo. Integrating LoRa-Based Communications into Unmanned Aerial Vehicles for Data Acquisition from Terrestrial Beacons. *Electronics*, 2022. https://doi.org/10.3390/electronics11121865
270. Poorvi, Joshi; Kalita, Alakesh; Gurusamy, Mohan. Reliable and Efficient Data Collection in UAV-Based IoT Networks. *IEEE Communications Surveys & Tutorials*, 2026. https://doi.org/10.1109/comst.2025.3550274
271. Zhang, Zheng; Zhou, Chun; Sheng, Liangcai; Cao, Shouqi. Optimization Schemes for UAV Data Collection with LoRa 2.4 GHz Technology in Remote Areas without Infrastructure. *Drones*, 2022. https://doi.org/10.3390/drones6070173
