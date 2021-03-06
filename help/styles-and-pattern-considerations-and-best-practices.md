---
title: Best practices and considerations 
seo-title: Best practices and considerations 
description: Best practices and considerations for Automated Forms Conversion service
seo-description: List of styles and patterns in source PDF forms which Automated Forms Conversion service finds difficult to identify
uuid: e24773a2-be14-4184-a168-48aa976d459a
topic-tags: introduction
discoiquuid: 79f2026e-73a5-4bd1-b041-d1399b4ad23e
---

# Best practices and known complex patterns {#Best-practices-and-considerations2}

This document provides guidelines and recommendations that forms administrator, authors, and developers can benefit from when working with Automated Forms Conversion service. It discusses best practices right from preparing source forms to fixing complex patterns that require some extra effort for automated conversion. These best practices collectively contribute to the overall performance and ouput of Automated Forms Conversion service.

## Best Practices

The conversion service converts PDF forms available on your AEM Forms instance to adaptive forms. You can upload all the PDF forms at once or in a phased manner, as required. Before uploading the forms, consider the following:

* Keep the number of forms in a folder less than 15 and keep the total number of pages in a folder less than 50.
* Keep the size of folder less than 10 MB. Do not keep forms in a sub-folder.
* Keep the number of pages in a form less than 15.
* Do not upload the protected forms. The service does not convert password-protected and secured forms.
* Do not upload the [PDF Portfolios](https://helpx.adobe.com/acrobat/using/overview-pdf-portfolios.html). The service does not convert a PDF Portfolio to an adaptive forms.
* Do not upload scanned, coloured, non-English language, and filled forms. Such forms are not supported.
* Do not upload source forms with spaces in the filename. Remove the space from the name of the file before uploading the forms.
* Use adaptive form templates to specify header and footer for the output adaptive form. The service ignores header-footer of source PDF documents and uses header-footer specified in the adaptive form template.

## Know complex patterns

AEM Forms Automated Conversion service uses artificial intelligence and machine learning algorithms to understand the layout and fields of the source form. Every machine learning service continuously learns from source data and produces an improved output with every churn. These services learn from the experience like humans.

Automated Forms Conversion service is trained on a large set of forms. It easily identifies fields in a source form and produces adaptive forms. However, there are some fields and styles in PDF forms which are easily visible to the human eye but difficult to understand for the service. The service can assign different than applicable field types or panels to some fields or styles. All such field and style patterns are listed below.

The service would start identifying and assigning correct fields or panels to these patterns as it keeps learning from the source data. For the time being, you can use [Review and Correct](review-correct-ui-edited.md) editor to fix such issues. Before start fixing the issues or reading further, familiarize yourself with [adaptive form components](https://helpx.adobe.com/experience-manager/6-5/forms/using/introduction-forms-authoring.html).

### General patterns {#general}

|Pattern|Resolution|
|--- |--- |
|**Pattern** <br> Service does not convert colored PDF forms to adaptive form. <br><br>**Resolution** <br> Use black and white or grayscale PDF forms.|![Coloured Form](assets/best-practice-coloured-forms.png)|
|**Pattern** <br>Service does not convert filled PDF forms to adaptive form. <br><br>**Resolution** <br>Use empty adaptive forms.| ![Filled Form](assets/best-practice-filled-forms.png) |
|**Pattern** <br>Service can fail to recognize text and fields in a dense form. <br><br>**Resolution** <br> Increase the width between text and fields of a dense form before starting the conversion.||
|**Pattern** <br>Service does not support scanned forms. <br><br>**Resolution** <br>Do not use scanned forms.|![Scanned Form](assets/scanned-forms.png)| 
|**Pattern** <br>Service does not extract images and text within images. <br><br>**Resolution** <br> Manually add images or text to converted forms.|![Image with text Form](assets/best-practice-image-with-text.png)|
|**Pattern** <br>Tables with dotted or non-clear boundaries and borders do not convert. <br><br>**Resolution** <br>Use tables with clear explicit boundaries and borders. supported.|![Non-clear table Form](assets/best-practice-table-dotted-non-clear.png) |
|**Pattern** <br> Adaptive form does not support vertical text out of the box. So, the service does not convert vertical text to corresponding Adaptive Forms text. <br><br>**Resolution** <br> Use adaptive form editor to add vertical text, if required. |![Non-clear table Form](assets/vertical-text.png) |



### Choice Group  {#choice-group}

|Pattern|Resolution|
|--- |--- |
|**Pattern** <br> Choice group options with shapes other than box or circle are not converted to corresponding adaptive form components. <br><br>**Resolution** <br> Change choice options shapes to box or circle or use Review and Correct editor to identify the shapes.|![Choice fileds ](assets/best-practice-choice-group-options.png) |

### Form fields {#form-fields}

|Pattern|Resolution|
|--- |--- |
|**Pattern** <br> Service does not identify fields without clear borders. <br><br>**Resolution** <br> Use Review and Correct editor to identify such fields.|![fileds wih non-clear boundaries](assets/best-practice-fields-without-clear-borders.png) |
|**Pattern** <br> Service may not identify some choice group form fields with captions at the bottom or right side of a form. <br><br>**Resolution** <br> Use Review and Correct editor to identify such fields| ![Choice fileds](assets/best-practice-caption-bottom-right.png)|
|**Pattern** <br> Service merges or assigns a wrong type to some form fields which are placed very near to each other or do not have clear borders. <br><br>**Resolution** <br> Use Review and Correct editor to identify such fields.|![Choice fileds](assets/best-practice-placed-very-near.png) |
|**Pattern** <br> Service can fail to recognize fields with far away captions or a dotted line between the caption and input field. <br><br>**Resolution** <br> Use forms fields with clear boundaries or use Review and Correct editor to fix such issues.|![Far away fields or dotted line between field of caption](assets/best-practice-far-away-captions-or-a-dotted-line.png) |

### Lists {#lists}

|Pattern|Resolution|
|--- |--- |
|**Pattern** <br>Lists containing form fields are merged or not converted to corresponding adaptive form components <br><br>**Resolution** <br>Use forms fields with clear boundaries or use Review and Correct editor to fix such issues.|![lists containing choice groups](assets/best-practice-lists-containing-form-fields.png)|
|**Pattern** <br>Service can leave a few nested lists unidentified <br><br>**Resolution** <br> Use Review and Correct editor to fix such issues.|![lists containing choice groups](assets/best-practice-nested-lists.png)|
|**Pattern** <br> Service merges some lists containing choice groups with each other <br><br>**Resolution** <br> Use Review and Correct editor to fix such issues.|![lists containing choice groups](assets/best-practice-check-box-in-table-cells.png)  |

<!--
Comment Type: draft

<h3>Choice groups</h3>
-->

<!--
Comment Type: draft

<ul>
<li>Lists with form fields, nested lists, and nested choice groups are not supported.</li>
<li>Form fields with captions at bottom or right are not supported.</li>
<li>Form fields without borders are not supported.</li>
<li>Hidden form fields are not supported.</li>
<li>Button in PDF forms are not converted to adaptive form buttons.<br /> </li>
<li>Tables with clear explicit boundaries and borders are supported.</li>
<li>Fields with far away captions are not supported.<br /> </li>
<li>Choice groups with only box or circle shaped selectors are supported. </li>
</ul>
-->
