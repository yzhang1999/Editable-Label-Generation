# Editable-Label-Generation

## Table of Contents
- [Project Description](#project-description)
- [Files Description](#files-description)
- [Process Workflow](#process-workflow)
- [Model Explanation](#model-explanation)
- [Feed Information to API and ZPL Code Generation](#feed-information-to-api-and-zpl-code-generation)
- [Contributors](#contributors)


## Project Description
The primary problem this project aims to solve is the inefficiency and complexity involved in the manual creation and modification of labels for Zebra printers. To address this, the project will develop an advanced automated system that leverages Generative AI to convert images of printer labels into Zebra Printer Language (ZPL).

## Files Description
- API.ipynb: This file includes code for prompt engineering and experiments with the Anthropic API and OpenAI API to generate ZPL code.

## Process Workflow
![Editable_Label_Workflow](https://github.com/user-attachments/assets/7136da11-c04b-44af-914d-51e3aae075a6)

## Model Explanation
### Image Detection using YOLO
[Inu]
### Optical Character Recognition
[Darwin]
### Image Recognition
[Louise]

## Feed Information to API and ZPL Code Generation
The final phase of this project was to identify and refine the optimal approach for generating ZPL code from label data, including text, bounding boxes, and barcode metadata. Through systematic exploration and prompt engineering, the OpenAI API was selected as the most effective solution for generating structured ZPL outputs. 

To identify the best-performing API for generating ZPL code from label data, initial trials were conducted with two platforms: OpenAI API (gpt-4o) and Anthropic API (claude-3.5-sonnet). The OpenAI API demonstrated strong performance in handling multi-modal inputs, such as bounding boxes, text, and barcode data, and consistently generated relevant and well-structured ZPL outputs. In contrast, the Anthropic API showed limited promise in producing structured ZPL code, often failing to handle the complex metadata effectively. After a thorough comparative analysis, the OpenAI API was selected for its superior ability to integrate diverse data types and deliver accurate and consistent results, making it the optimal choice for this project.

*Baseline Experimentation*

In the baseline approach, a general prompt was used to detect metadata (e.g., text, figures, and barcodes) and generate ZPL code. While the API produced functional outputs, the lack of structured input data, such as bounding box coordinates, resulted in imprecise label formatting. OpenAI API consistently outperformed Anthropic, delivering more structured and relevant outputs, but the results highlighted the need to incorporate spatial context for improved precision.

*Incorporating Bounding Box Information*

To address the lack of spatial context in the baseline approach, bounding box data was introduced to provide precise location information for text and barcodes. This enhancement allowed the API to generate ZPL code with improved accuracy in element alignment and formatting. The initial challenge was that the baseline prompt lacked contextual details about object placement, leading to inconsistencies in the output. By integrating bounding box coordinates into the prompt, the API was able to understand spatial relationships, resulting in significantly enhanced precision and accurate positioning of label elements.

*Adding Text Metadata*

Building on the integration of bounding box data, textual content was added to provide semantic clarity, enabling the API to interpret and align text elements with their respective bounding boxes more effectively. The initial challenge was that the API required explicit textual data to fully understand the label content. To address this, both bounding box and text information were incorporated into the prompt. This enhancement improved the API's comprehension of the label structure, leading to better alignment and a more accurate representation of text elements in the ZPL output.

*Enhancing Prompts with Barcode Data*

Building on the integration of bounding box and text data, barcode information was incorporated into the prompts to provide critical structural and validation data for the API. The barcode metadata, including type and count, was essential for ensuring that the generated ZPL code accurately represented the expected label format. The initial challenge was that the absence of explicit barcode details in the prompts limited the API's ability to validate and generate precise outputs for barcode elements. By including this metadata extracted from the Pyzbar model, the API was able to accurately identify, encode, and position barcodes within the label. This enhancement improved the reliability of the ZPL code generation process by ensuring that the barcodes matched the input expectations in terms of type, count, and placement, thereby reducing errors and improving label accuracy.

*Key Findings and Learnings*

Throughout the project, several critical insights and advancements were made, which significantly enhanced the performance and reliability of the ZPL code generation pipeline. Incremental prompt engineering proved to be a powerful tool, allowing us to systematically refine API outputs and address specific challenges. Integrating bounding box and text metadata into the prompts was a key breakthrough, as it provided spatial and semantic context, enabling the API to produce more accurate and well-structured ZPL code. Furthermore, incorporating barcode information into the workflow not only improved the accuracy of barcode elements but also facilitated output validation by ensuring alignment with the expected label structure. These findings highlight the importance of iterative development and the value of combining multiple data modalities to optimize AI-driven solutions.

## Contributors
- Yumin Zhang
- Inu Tenneti
- Louise Liu
- Darwin Ye
