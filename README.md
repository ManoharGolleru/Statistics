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

    %% Continuous Dependent Variable
    G --> J{Number of Groups}
    J --> K[Two Groups]
    J --> L[More than Two Groups]

    %% Two Groups
    K --> M{Are Groups Independent}
    M --> N[Independent]
    M --> O[Paired or Related]

    %% Independent Groups
    N --> P{Is Sample Size Large}
    P --> Q[Yes]
    P --> R[No]

    Q --> S{Assume Normality and Equal Variance}
    S --> T[Yes]
    S --> U[No]

    T --> V[Independent Samples t-test]
    U --> W[Check Assumptions]

    W --> X{Normality Test}
    X --> Y{Data Normally Distributed}
    Y --> Z[Yes] --> AA{Variance Test}
    AA --> AB{Equal Variances}
    AB --> AC[Yes] --> AD[Independent Samples t-test]
    AB --> AE[No] --> AF[Welch's t-test]
    Y --> AG[No] --> AH[Mann-Whitney U test]

    R --> AH[Mann-Whitney U test]

    %% Paired Groups
    O --> AI{Sample Size Large}
    AI --> AJ[Yes]
    AI --> AK[No]

    AJ --> AL{Normality of Differences}
    AL --> AM[Yes] --> AN[Paired Samples t-test]
    AL --> AO[No] --> AP[Wilcoxon Signed-Rank test]

    AK --> AP[Wilcoxon Signed-Rank test]

    %% More than Two Groups
    L --> AQ{Are Groups Independent}
    AQ --> AR[Independent]
    AQ --> AS[Repeated Measures]

    %% Independent Groups
    AR --> AT{Assume Normality and Equal Variance}
    AT --> AU[Yes] --> AV[One-Way ANOVA]
    AT --> AW[No] --> AX[Check Assumptions]

    AX --> AY{Normality Test}
    AY --> AZ{Data Normally Distributed}
    AZ --> BA[Yes] --> BB{Variance Test}
    BB --> BC{Equal Variances}
    BC --> BD[Yes] --> AV[One-Way ANOVA]
    BC --> BE[No] --> BF[Welch's ANOVA]
    AZ --> BG[No] --> BH[Kruskal-Wallis test]

    %% Repeated Measures
    AS --> BI{Assume Sphericity}
    BI --> BJ[Yes] --> BK[Repeated Measures ANOVA]
    BI --> BL[No] --> BM[Apply Correction]
    BM --> BK[Repeated Measures ANOVA]
    BI --> BN[No] --> BO[Friedman test]

    %% Categorical Dependent Variable
    H --> BP{Type of Categorical Variable}
    BP --> BQ[Dichotomous]
    BP --> BR[More than Two Categories]
    BP --> BS[Ordinal]

    %% Dichotomous Variable
    BQ --> BT{Expected Frequencies Large}
    BT --> BU[Yes] --> BV[Chi-Square Test]
    BT --> BW[No] --> BX[Fisher's Exact Test]

    %% More than Two Categories
    BR --> BY[Chi-Square Test]

    %% Ordinal Variable
    BS --> BZ[Mann-Whitney U or Kruskal-Wallis test]

    %% Counts Data
    I --> CA{Type of Counts Data}
    CA --> CB[Poisson Distribution]
    CA --> CC[Overdispersed]

    CB --> CD[Poisson Regression]
    CC --> CE[Negative Binomial Regression]

    %% Relationships
    D --> CF{Type of Variables}
    CF --> CG[Both Continuous]
    CF --> CH[One Continuous, One Categorical]
    CF --> CI[Both Categorical]
    CF --> CJ[Time-to-Event Data]

    %% Both Continuous
    CG --> CK{Linear Relationship}
    CK --> CL[Yes] --> CM{Data Normally Distributed}
    CM --> CN[Yes] --> CO[Pearson Correlation]
    CM --> CP[No] --> CQ[Spearman Correlation]
    CL --> CP[No] --> CQ[Spearman Correlation]

    %% Continuous and Categorical
    CH --> CR[Point-Biserial or ANOVA]

    %% Both Categorical
    CI --> CS[Chi-Square Test of Independence]

    %% Time-to-Event Data
    CJ --> CT[Survival Analysis]

    %% Predicting Outcomes
    E --> CU{Type of Outcome Variable}
    CU --> CV[Continuous]
    CU --> CW[Categorical]
    CU --> CX[Count Data]
    CU --> CY[Time-to-Event]

    %% Continuous Outcome
    CV --> CZ{Assumptions Met}
    CZ --> DA[Yes] --> DB[Linear Regression]
    CZ --> DC[No] --> DD[Transform or Non-parametric]

    %% Categorical Outcome
    CW --> DE{Binary or Multiclass}
    DE --> DF[Binary] --> DG[Logistic Regression]
    DE --> DH[Multiclass] --> DI[Multinomial Logistic Regression]
    DE --> DJ[Ordinal] --> DK[Ordinal Regression]

    %% Count Data Outcome
    CX --> DL{Distribution of Counts}
    DL --> DM[Poisson Distribution] --> DN[Poisson Regression]
    DL --> DO[Overdispersion] --> DP[Negative Binomial Regression]

    %% Time-to-Event Outcome
    CY --> DQ[Survival Analysis]

    %% Covariance Analysis
    AV & BD --> DR{Interested in Covariates}
    DR --> DS[Yes] --> DT[ANCOVA]
    DR --> DU[No] --> DV[ANOVA]

    %% End
    AD & AF & AH & AN & AP & AV & BF & BH & BK & BO & BV & BX & BY & BZ & CD & CE & CO & CQ & CR & CS & CT & DB & DD & DG & DI & DK & DN & DP & DQ & DT & DU --> DW[End]
