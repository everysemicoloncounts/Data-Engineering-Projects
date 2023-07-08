A public data lake for analysis of COVID-19 data
by AWS Data Lake Team | on 08 APR 2020 | in Amazon Athena, Amazon QuickSight, Analytics, AWS Big Data, AWS CloudFormation, AWS Data Exchange, AWS Glue, AWS Lake Formation, Serverless, Top Posts | Permalink | Comments |  Share

As the COVID-19 pandemic continues to threaten and take lives around the world, we must work together across organizations and scientific disciplines to fight this disease. Innumerable healthcare workers, medical researchers, scientists, and public health officials are already on the front lines caring for patients, searching for therapies, educating the public, and helping to set policy. At AWS, we believe that one way we can help is to provide these experts with the data and tools needed to better understand, track, plan for, and eventually contain and neutralize the virus that causes COVID-19.

Today, we are making a public AWS COVID-19 data lake available – a centralized repository of up-to-date and curated datasets on or related to the spread and characteristics of the novel corona virus (SARS-CoV-2) and its associated illness, COVID-19. Globally, there are several efforts underway to gather this data, and we are working with partners to make this crucial data freely available and keep it up-to-date. Hosted on the AWS cloud, we have seeded our curated data lake with COVID-19 case tracking data from Johns Hopkins and The New York Times, hospital bed availability from Definitive Healthcare, and over 45,000 research articles about COVID-19 and related coronaviruses from the Allen Institute for AI. We will regularly add to this data lake as other reliable sources make their data publicly available.

The breakthroughs that can win the battle against this disease arrive faster when it’s easy for everyone to access and experiment with this vital information. The AWS COVID-19 data lake allows experimenters to quickly run analyses on the data in place without wasting time extracting and wrangling data from all the available data sources. They can use AWS or third-party tools to perform trend analysis, do keyword search, perform question/answer analysis, build and run machine learning models, or run custom analyses to meet their specific needs. Since every stakeholder in this battle brings their own perspective, users can choose to work with the public data lake, combine it with their own data, or subscribe to the source datasets directly through AWS Data Exchange.

We imagine local health authorities could build dashboards to track infections and collaborate to efficiently deploy vital resources like hospital beds and ventilators. Or epidemiologists could complement their own models and datasets to generate better forecasts of hotspots and trends.

For example, at Chan Zuckerberg Biohub, a nonprofit where leaders in science and technology collaborate to cure, prevent, or manage disease, scientists are using the AWS COVID-19 data lake for new epidemiological insights. “Our team of researchers is now analyzing trends in disease spread, its geography, and time evolution by leveraging datasets from the AWS COVID-19 data lake, combined with our own data, in order to better predict COVID epidemiology,” said Jim Karkanias, Vice President of Data Science and Information Technology at Chan Zuckerberg Biohub.

This post walks you through examples of how to use the AWS COVID-19 data lake for analysis. This data lake is comprised of data in a publicly readable Amazon S3 bucket (s3://covid19-lake). The post shows how to set up the definitions for that data in an AWS Glue Data Catalog to expose it to analytics engines. You can then query the AWS COVID-19 data lake with Amazon Athena, a serverless SQL query engine.
Prerequisites

This post assumes you have the following:

    Access to an AWS account
    Permissions to create an AWS CloudFormation stack
    Permissions to create AWS Glue resources (catalog databases and tables)

Configuring access to the data using a CloudFormation template

To make the data from the AWS COVID-19 data lake available in the Data Catalog in your AWS account, create a CloudFormation stack using the following template. If you are signed in to your AWS account, the following link fills out most of the stack creation form for you. All you need to do is choose Create stack. For instructions on creating a CloudFormation stack, see Get Started in the Cloud Formation documentation.

This template creates a covid-19 database in your Data Catalog and tables that point to the public AWS COVID-19 data lake. You do not need to host the data in your account, and you can rely on AWS to refresh the data as datasets are updated through AWS Data Exchange.
Exploring the data through the Data Catalog in your AWS account

When the CloudFormation stack shows a status of CREATE_COMPLETE, access the Glue Data Catalog to see the tables that the template created. You should see the following tables:

    Global Coronavirus (COVID-19) Data – Tracks confirmed COVID-19 cases in provinces, states, and countries across the world with a breakdown to the county level in the US.
    Coronavirus (COVID-19) Data in the United States – Tracks confirmed cases and deaths in the US by state and county.
    Coronavirus Disease (COVID-19) Testing Data – Tracks the number of people tested, pending tests, and positive and negative tests for COVID-19.
    USA Hospital Beds – COVID-19 – Data on hospital beds and their utilization in the US.
    Lookup tables to support visualizations.
        country_codes -- Lookup table for country codes
        country_populations -- Lookup table for the population for each county based on recent census data
        us_state_abbreviations -- Lookup table for US state abbreviations

In addition, you can see descriptions of the columns in these tables. For example, the following screenshot shows the metadata of the table containing COVID-19 cases from Johns Hopkins.
