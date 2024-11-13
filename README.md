# Statistics
```mermaid
flowchart TD
    %% Start
    A[Start] --> B{Define Research Question}

    %% Research Question Types
    B --> C[Comparing Groups]
    B --> D[Assessing Relationships]
    B --> E[Predicting Outcomes]

    %% Comparing Groups
    C --> F{Dependent Variable Type}
    F --> G[Continuous]
    F --> H[Categorical]
    F --> I[Counts]

    %% Dependent Variable is Continuous
    G --> J{Number of Groups}
    J --> K[Two Groups]
    J --> L[More than Two Groups]

    %% Two Groups
    K --> M{Are Groups Independent?}
    M --> N[Independent]
    M --> O[Paired or Related]

    %% Independent Groups
    N --> P{Sample Size Adequate?}
    P --> Q[Yes]
    P --> R[No]

    Q --> S{Assume Normality and Equal Variance?}
    S --> T[Yes]
    S --> U[No]

    T --> V[**Independent Samples t-test**]
    U --> W[Check Assumptions]

    W --> X{Normality Test (e.g., Shapiro-Wilk)}
    X --> Y{Data Normally Distributed?}
    Y --> Z[Yes] --> AA{Homogeneity of Variance Test (e.g., Levene's Test)}
    AA --> AB{Equal Variances?}
    AB --> AC[Yes] --> AD[**Independent Samples t-test**]
    AB --> AE[No] --> AF[**Welch's t-test**]
    Y --> AG[No] --> AH[**Mann-Whitney U test**]

    R --> AH[**Mann-Whitney U test**]

    %% Paired Groups
    O --> AI{Sample Size Adequate?}
    AI --> AJ[Yes]
    AI --> AK[No]

    AJ --> AL{Normality of Differences?}
    AL --> AM[Yes] --> AN[**Paired Samples t-test**]
    AL --> AO[No] --> AP[**Wilcoxon Signed-Rank test**]

    AK --> AP[**Wilcoxon Signed-Rank test**]

    %% More than Two Groups
    L --> AQ{Are Groups Independent?}
    AQ --> AR[Independent]
    AQ --> AS[Repeated Measures]

    %% Independent Groups
    AR --> AT{Assume Normality and Equal Variance?}
    AT --> AU[Yes] --> AV[**One-Way ANOVA**]
    AT --> AW[No] --> AX[Check Assumptions]

    AX --> AY{Normality Test}
    AY --> AZ{Data Normally Distributed?}
    AZ --> BA[Yes] --> BB{Homogeneity of Variance Test}
    BB --> BC{Equal Variances?}
    BC --> BD[Yes] --> AV[**One-Way ANOVA**]
    BC --> BE[No] --> BF[**Welch's ANOVA**]
    AZ --> BG[No] --> BH[**Kruskal-Wallis test**]

    %% Repeated Measures
    AS --> BI{Assume Sphericity? (Mauchly's Test)}
    BI --> BJ[Yes] --> BK[**Repeated Measures ANOVA**]
    BI --> BL[No] --> BM[Apply Correction (e.g., Greenhouse-Geisser)]
    BM --> BK[**Repeated Measures ANOVA**]
    BI --> BN[No] --> BO[**Friedman test**]

    %% Dependent Variable is Categorical
    H --> BP{Type of Categorical Variable}
    BP --> BQ[Dichotomous]
    BP --> BR[More than Two Categories]
    BP --> BS[Ordinal]

    %% Dichotomous Variable
    BQ --> BT{Expected Frequencies ≥ 5?}
    BT --> BU[Yes] --> BV[**Chi-Square Test**]
    BT --> BW[No] --> BX[**Fisher's Exact Test**]

    %% More than Two Categories
    BR --> BY[**Chi-Square Test**]

    %% Ordinal Variable
    BS --> BZ[**Mann-Whitney U test** or **Kruskal-Wallis test**]

    %% Counts Data
    I --> CA{Type of Counts Data}
    CA --> CB[Poisson Distribution]
    CA --> CC[Overdispersed]

    CB --> CD[**Poisson Regression**]
    CC --> CE[**Negative Binomial Regression**]

    %% Assessing Relationships
    D --> CF{Type of Variables}
    CF --> CG[Both Continuous]
    CF --> CH[One Continuous, One Categorical]
    CF --> CI[Both Categorical]
    CF --> CJ[Time-to-Event Data]

    %% Both Continuous Variables
    CG --> CK{Linear Relationship?}
    CK --> CL[Yes] --> CM{Data Normally Distributed?}
    CM --> CN[Yes] --> CO[**Pearson Correlation**]
    CM --> CP[No] --> CQ[**Spearman Correlation**]
    CL --> CP[No] --> CQ[**Spearman Correlation**]

    %% One Continuous, One Categorical Variable
    CH --> CR[**Point-Biserial Correlation** or **t-test/ANOVA**]

    %% Both Categorical Variables
    CI --> CS[**Chi-Square Test of Independence**]

    %% Time-to-Event Data
    CJ --> CT[**Survival Analysis** (e.g., Cox Proportional Hazards Model)]

    %% Predicting Outcomes
    E --> CU{Type of Outcome Variable}
    CU --> CV[Continuous]
    CU --> CW[Categorical]
    CU --> CX[Count Data]
    CU --> CY[Time-to-Event Data]

    %% Continuous Outcome
    CV --> CZ{Assumptions Met?}
    CZ --> DA[Yes] --> DB[**Linear Regression**]
    CZ --> DC[No] --> DD[Consider Transformation or Non-parametric Regression]

    %% Categorical Outcome
    CW --> DE{Binary or Multiclass?}
    DE --> DF[Binary] --> DG[**Logistic Regression**]
    DE --> DH[Multiclass] --> DI[**Multinomial Logistic Regression**]
    DE --> DJ[Ordinal] --> DK[**Ordinal Regression**]

    %% Count Data Outcome
    CX --> DL{Distribution of Counts}
    DL --> DM[Poisson Distribution] --> DN[**Poisson Regression**]
    DL --> DO[Overdispersion] --> DP[**Negative Binomial Regression**]

    %% Time-to-Event Outcome
    CY --> DQ[**Survival Analysis** (e.g., Cox Proportional Hazards Model)]

    %% Covariance Analysis
    AV & BD --> DR{Interested in Covariates?}
    DR --> DS[Yes] --> DT[**ANCOVA** (Analysis of Covariance)]
    DR --> DU[No] --> DV[Proceed with ANOVA]

    %% End
    AD & AF & AH & AN & AP & AV & BF & BH & BK & BO & BV & BX & BY & BZ & CD & CE & CO & CQ & CR & CS & CT & DB & DD & DG & DI & DK & DN & DP & DQ & DT & DU --> DW[End]
