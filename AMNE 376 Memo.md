
## Image-Embeddings and Applications about Greek Arts and Architectures

### Problems to Ask and Answer
- **Can Hugging Face models correctly cluster and classify the age of objects given high resolution images or scanned models?**
- **What other features can Image-Embedding help us to find, such as the similarity and the distinctions between arts and architectures of different cultures and different eras?** 
- **Can models without fine-tuning correctly cluster arts given their images? What would be the pivot of clustering?** 
- **Given the description/documentations of an artwork, can AI models correctly classify their corresponding culture, age, genre, and even match the image of the actual object?**
- **Given the archeological illustrations, diagrams and maps as training materials, can a fine-tuned models correctly classify photos of architectures?**

### Potential Data Sources

- **UBC MOA** -> The collections lack of big items such as statues and marble sarcophagus.
- [**The Metropolitan Museum of Art**](https://www.metmuseum.org/art/collection) -> We can access the collections with high resolution images with its api, but we still lack a large amount of data needed, also no architecture. 
- **Google Arts & Culture** -> Rich data but no api provided, might be risky to scrape.
- [**Getty Open Content Program**](https://www.getty.edu/art/collection/search?open_content=true) -> has a reasonable amount of collections, but the format isn't as standardized as the MET.
- [**American School of Classical Studies at Athens**](https://www.ascsa.edu.gr/research/personal-papers-and-archives/photographic-collection)-> A rich collection of photographs shot by archeologists including many architectures, but the data doesn't contain much text descriptions or information about the age of the objects. Many photos are low-resolution. **More serious: the photos are copyrighted, we should avoid the potential legal risks.**
- [**Harvard Art Museum**](https://harvardartmuseums.org/collections)-> We can access a large number of greek, roman and egyptian collections with its api. Very convenient query process. May be fit for the api notebook. **However, the api may require individual registration.** We can also obtain data and images for sculptures, pottery and coins from here. 
- [**Ancient Greece.org**]([https://ancient-greece.org/history/ancient-greece-timeline-through-pictures/)-> The website has a rich text and image content about all aspects of Ancient Greece, however, it doesn't provide an api to the public. The page [Ancient Greece Timeline In Pictures]([Ancient Greece Timeline In Pictures – Ancient Greece: Φώς & Λέξη](https://ancient-greece.org/history/ancient-greece-timeline-through-pictures/)) may be a good resource for practicing web scraping.
### Pedagogical Planning and Project Design

- **Data Collecting**: We are aiming at obtaining a dataset of Greek artworks and architectures of different eras and of different types, with high resolution images/scanned models of the objects, information of the estimated age and the location where they were discovered, such that we can use the data to validate the credibility of classification/clustering. ***Currently, I used my api key to query and downloaded a large dataset with 1538 image objects from the Harvard Art Museum collections.***

- **Pedagogical Design**: We should understand how this relates to and would extend the current materials of the course, introducing students to the advanced field of archeology and classic study with AI/Machine Learning on a solid way that align with their academic background. The teaching should be interactive and potentially transitive into their course project and future courseworks. **We would always need to decide in which part of the course we are going to fit in these new materials. In class? Assignment? Discussion? Special Lectures?*** 

- **Material Design**: We will need an interactive form that can demonstrate how AI would change the way how people study history and archeology without being too technical (since we can always assume AMNE students are not so familiar with programing and software). The high requirement of computational power for word/image embedding is also of great concern. Ideally, we will need an all accessible way to carry out cloud compuation. **Worst case scenario, we may just create a demo for displaying in class.**

- **Format of Notebooks:** Notebooks should be fun and interactive, and still be accessible to students who lack computer skills. In addition to this, the notebooks should be accessible to the students even after they have finished the course and should not be limited by hardware constraints. I envision that we should follow the example of the DSCI 100 worksheet and simplify it even further. For example, provide code lines as options, and make the sections of the notebook that need to be run manually fill-in-the-blanks, supplemented by multiple-choice questions for post-course practice. Beyond that, we should also provide a basic workable template for students who are interested in learning the content on their own to explore on their own, or even encourage them to use it in their course-related projects.
### Notebook Plans

Carrier of the notebooks: Currently the best way for students to get access to gpus with web browser is through **Google Colab**. However, whether this complies the security requirement of UBC remains for further discussions. 

#### Notebook 1: Introduction to jupyter notebook, api and web scraping

- This notebook written in python should provide students with a basic introduction to jupyter notebook and its runtime environment, api and web scraping. It should aim to provide students with an understanding of basic programming concepts and introduce them to the benefits of learning programming and AI-related tools for art history and archaeology research through practical examples of using api's and crawlers to efficiently access information and web resources.

- The first part of the notebook will introduce the structure of a jupyter notebook, basic shortcuts, and how the cell is run. This section may include one or two fill-in-the-blanks that students need to complete, as well as multiple-choice questions to check their understanding.

- The second section will provide students with a complete api query template, as well as links to the websites that need to be accessed using the api, and a summary of the api documentation. Students will be prompted to review the website and documentation and enter the required api key/base url to complete a successful api call. students will also be introduced to path formatting, how to access downloaded files, how to read json or csv files, etc. in this section. This section should also include multiple choice questions to check understanding. 

- The third section can be an optional project, where the notebook should provide a complete crawler to allow students to crawl and download image resources that are not accessible through the api, while adhering to information access policies and copyrights.

#### Notebook 2: Introduction to image embedding and classification -- Using images of Greek sculptures as examples.

- This notebook will continue where the previous one left off, introducing students to some of the basics of AI and machine learning. We will provide a dataset that includes images of ancient Greek sculptures from different eras and cultures, as well as some Egyptian, Roman, and Renaissance sculptures, for students to try basic data exploration and image embedding. This notebook will still be primarily in fill-in-the-blank format, supplemented by multiple-choice questions as a means of testing students' understanding and mastery.

- In this notebook, we will probably not use a fine tuned model, but rather a base model for differentiation in order to ensure efficient operation. Due to the complexity of the content and concept, we may need to focus on visual diagrams in this notebook, through a large number of visualizations to show how quantitative image embedding can be used to distinguish sculptures from different eras or cultures through the features of the images, and in this way, to introduce the basic concepts of classification. 

- For the sake of fun, a process of having students manually classify the sculptures could also be included, and eventually comparing the accuracy of manual classification with that of the AI model through statistical data. In the end of the notebook, fine-tuning can be introduced as an optional section.

#### Notebook 3: Introduction to Clustering by image embedding -- Using images of pottery and coins as examples

- In addition to sculpture, pottery and coins were equally important in Ancient Greek art and culture and underwent significant development from the Bronze Age onwards. Many of the coins and pottery artifacts are incompletely preserved and are often found as sherds. Therefore, we can show how they can be clustered and analyzed with the help of machine learning methods.

- In this notebook, we will provide students with an opportunity to explore a complete dataset of images of pottery and coins and their fragments, and introduce them to clustering using the BERT model, with plenty of visualizations to aid their understanding. Students will get to see how clustering unveil the hidden features not directly visible by image embeddings, and they can try out clustering with the datasets they scraped on their own and that from the previous notebook as well.

- We can include a pre-trained fine-tuned model in the notebook and draw comparison between it and the base model, so students can understand the difference quality of models with only pre-trained data and with fed data for specific tasks.

#### Notebook 4: Introduction to zero-shot prompting and LLM -- Using images and maps of Greek architectures as examples

TBD (I can't think of a very good example of what we are going to do with architectures actually.)

### Learning Outcomes

- Students will gain a basic understanding of how computer science, as well as artificial intelligence/machine learning techniques can be applied to art history/archaeology research and develop a critical perspective on how technology is reshaping scholarly approaches to arts and humanities research.
- Students get to learn more about handling digital “objects” (images & metadata) as evidence, as well as critiquing model limits. This also enables students to discover, contextualize and interpret scholarly results from a broader vision. 
### Reference
- Castellano, G., Vessio, G. A Deep Learning Approach to Clustering Visual Arts.  _Computer Vision and Cultural Heritage Preservation 16 August 2022 Volume 130_, pages 2590–2605, (2022) <https://doi.org/10.1007/s11263-022-01664-y>
- Cetinic, E., Lipic, T., Grgic, S. Fine-tuning Convolutional Neural Networks for fine art classification. _Expert Systems with Applications Volume 114, 30 December 2018_, Pages 107-118 <https://doi.org/10.1016/j.eswa.2018.07.026>
- Resler, A., Yeshurun, R., Natalio, F. _et al._ A deep-learning model for predictive archaeology and archaeological community detection. _Humanit Soc Sci Commun_ **8**, 295 (2021). https://doi.org/10.1057/s41599-021-00970-z
- Zou, H.; Ge, J.; Liu, R.; He, L. Feature Recognition of Regional Architecture Forms Based on Machine Learning: A Case Study of Architecture Heritage in Hubei Province, China. _Sustainability 2023, 15_, 3504. <https://doi.org/10.3390/su15043504>
