# 📄 Problem Definition

**Problem Statement**

This project examines a multi-class classification problem: predicting corruption levels in countries (SDG 16 - Peace, Justice, and Strong Institutions).

**Hypothesis:**

Socioeconomic characteristics indicative of a country's overall level of development can reliably predict the target outcome.

**Social Relevance**

Corruption is a factor that distorts the functioning of a country. It affects the efficiency of public spending, trust in institutions, political stability, foreign investment, and, in general, economic and social development. However, measuring corruption directly is complicated: there are no "exact figures" like those for unemployment or inflation, but rather indices based on perception surveys or expert assessments.

If we could anticipate a country's level of corruption based on more objective variables such as press freedom, digitalization, educational level, dependence on natural resources, internet use, fiscal transparency, etc. then:

For governments: it would serve as an early warning and a guide for designing more effective public policies.

For international organizations and NGOs: it would allow for better targeting of aid and assessing the risk of project implementation.

For investors: it would provide signals about the legal security and stability of the business environment.

For researchers and citizens: it would open a space to understand patterns and question official narratives.

In short: the problem is that corruption is difficult to measure and even more difficult to combat; predicting it based on hard data would be a tool to expose hidden risks and make more informed decisions.

Accurate classification of this phenomenon is important because:

It helps policymakers and organizations make more informed decisions (e.g. resource allocation, targeted interventions).

It promotes transparency and accountability, reducing the risk of bias in decision-making.

It has a direct social impact (e.g. fair lending, equal access to healthcare, or corruption monitoring).

**Rationale for choosing classification over regression**

CPI (perception of corruption in general) and Political Corruption Index (a more focused metric), their “average” or composite is still arbitrary. The categories in this case are even more honest than regression on an artificial scale.

While corruption could be given as a number, for example between 0 and 100, this value does not reflect precise measurements of corruption, but aggregated perceptions gathered from surveys and expert assessments. Therefore, absolute differences between, for example, 42 and 44 do not have the same objective significance as differences between physical indicators (for example, temperature or height). The CPI is closer to an ordinal scale: it shows the relative position of a country, but does not guarantee a linear interpretation of the numbers.

If we use regression, the model will adjust to the imaginary accuracy of these arbitrary numbers. The result will be a forecast of “43.7”, although in reality no one can interpret it as anything other than “medium level of corruption”.

Therefore, the classification is more justified:

Interpretability - the low / medium / high / very high categories reflect how the CPI index is already used in analytics and the media.

Consistency with the nature of the data - we recognize the arbitrary nature of the numbers and reduce them to qualitative levels.

Social significance - it is easier for politicians, researchers and citizens to work with conclusions like 'the country is in the group with a high level of corruption' than with the conditional number '42.7'.

Thus, the classification not only reduces the risk of stretching the model to an unstable metric, but also makes the result closer to the real practice of using CPI.

**Dataset Justification**

The next datasets are selected for the problem:

- GDP Per Capita (Source: Worldbank)

- Average years of schooling (Source: ourworldindata.org)

- Inflation rate (Source: Worldbank)

- Internet use as % of population (Source: Worldbank)

- Political Corruption Index (Source: ourworldindata.org)

- Freedom of Press (Source: Worldbank)

- Natural Reources Rent as % of GDP (Source: Worldbank)

- Corruption Perception Index (Source: ourworldindata.org)

- Unemployment Rate (Source: Worldbank)

The selected datasets are well suited to the problem because:

Relevance: It contains useful characteristics that are highly related with the target outcome.

**Dataset Rationale**

The selected datasets are highly relevant for the task of predicting corruption because they reflect socioeconomic, political, and institutional characteristics that are closely correlated with the quality of public governance. Indicators such as GDP per capita, education, inflation, unemployment, press freedom, and internet use are frequently studied in the political economy literature as structural determinants of corruption. Together, they provide a multidimensional profile of a country's situation, allowing for more comprehensive and accurate modeling than using solely subjective corruption indices.

The dataset meets the following criteria:

Relevance:
The selected indicators (economic development, digital penetration, education level, institutional transparency, press freedom, and resource dependence) are directly related to anti-corruption outcomes. They offer at least five informative and complementary features, ensuring that the model reflects both economic and institutional dynamics.

Class Balance:
Corruption categories (low, medium, high, very high) are derived from the Corruption Perception Index and Political Corruption Index, which allows for a reasonable distribution of classes across multiple years and regions. Despite potential imbalances (e.g., fewer countries with "low corruption"), the dataset covers nearly a decade (2012–2021) and includes a diverse range of economies, reducing the risk of significant distributional bias. Methods such as class weighting or oversampling can further reduce imbalances in the training data.

**Ethical Risks:**

Using socioeconomic indicators to predict corruption raises ethical concerns. For example:

- Predictions can be misinterpreted to stigmatize certain regions or justify discriminatory policies.

- Bias Contagion: Input variables such as press freedom or education can encode existing inequalities, reinforcing stereotypes.

- Data Integrity Issues: Perception-based corruption indicators (e.g. the CPI) are inherently subject to cultural and political biases.

**To mitigate these risks:**

Sensitive country characteristics (e.g., ethnicity, religion, or political regime) are explicitly excluded from the feature set.

Class rebalancing methods (such as SMOTE or weighting factors) will be applied transparently, and model outputs will include uncertainty measures, mitigating the risk of overconfidence in unstable cases.

Forecasts should be interpreted at the aggregate or regional level for comparative analysis, rather than labeling individual countries as "corrupt," ensuring that the results are used to support policy and research rather than to create punitive labels.

With a clear strategy for mitigating risks related to relevance, class balance, and ethical concerns, the dataset is both highly suitable and socially responsible for use in this corruption forecasting task.
