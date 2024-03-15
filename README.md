## Image Captioning using KNN

Although VLMs (Vision Language Models) are the go to tools for image captioning right now, there are interesting works from earlier years that used KNN for captioning and perform surprisingly well enough!

Further, Libraries like [Faiss](https://engineering.fb.com/2017/03/29/data-infrastructure/faiss-a-library-for-efficient-similarity-search/) perform the nearest neighbor computation efficiently and are used in many industrial applications.

- Here, we will implement an algorithm to perform captioning using KNN based on the paper [A Distributed Representation Based Query Expansion Approach for
Image Captioning](https://aclanthology.org/P15-2018.pdf)

- Dataset: [MS COCO](https://cocodataset.org/#home) 2014 (val set only)

- Algorithm:
    1. Given: Image embeddings and correspond caption embeddings (5 Per image)
    2. For every image, findout the k nearest images and compute its query vector as the weighted sum of the captions of the nearest images (k*5 captions per image)
    3. The predicted caption would be the caption in the dataset that is closest to the query vector. 

- The image and text embeddings are extracted from the [CLIP](https://openai.com/research/clip) model.

- Tasks:
    1. Implement the algorithm and compute the bleu score. Use Faiss for nearest neighbor computation. Starter code is provided below.
    2. Try a few options for k. Record your observations.
    3. For a fixed k, try a few options in the Faiss index factory to speed the computation in step 2. Record your observations.
    4. Qualitative study: Visualize five images, their ground truth captions and the predicted caption.


---

Done as an assignment for the CS7.403: Statistical Methods in Artificial Intelligence (SMAI) course under Prof. Vineet Gandhi.