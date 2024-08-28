# ECoG-Reconstruction-from-Visual-Stimuli-A-Deep-Learning-Approach
**This project aims to reconstruct Electrocorticography (ECoG) data from visual stimuli using advanced deep learning techniques. 
We leverage the dataset from the seminal work "Timing, timing, timing: Fast decoding of object information from intracranial field potentials in human visual cortex" by Liu et al. (2009) (https://klab.tch.harvard.edu/resources/liuetal_timing3.html) to train and evaluate our model.
Our approach combines Convolutional Neural Networks (CNNs) and Graph Neural Networks (GNNs) to capture both the hierarchical processing of visual information and the complex interconnectivity of the brain's visual system**

*******The Visual System of the Brain:*******
The human visual system is a remarkably complex and efficient information processing network. To understand why we've chosen our particular model architecture, it's crucial to first examine the structure and function of the visual system.
Hierarchical Processing in the Visual Cortex Visual processing in the brain follows a hierarchical pathway, starting from the retina and proceeding through various cortical areas:

**Retina**: Light is converted into electrical signals by photoreceptors.
Lateral Geniculate Nucleus (LGN): Acts as a relay station, preprocessing visual information before it reaches the cortex.
Primary Visual Cortex (V1): The first cortical area to receive visual input, processing basic features like edges and orientations.
V2, V3, V4: These areas process increasingly complex features such as shapes, colors, and textures.
Higher Visual Areas (e.g., IT cortex): Responsible for complex object recognition and scene understanding.

This hierarchical structure allows for the gradual extraction and combination of visual features, from simple to complex. Each successive layer in the hierarchy combines information from previous layers to form more abstract representations of the visual input.
Parallel Processing and Interconnectivity
While the visual system exhibits a hierarchical structure, it's important to note that processing doesn't occur in a strictly serial manner. The visual cortex is characterized by extensive interconnectivity and parallel processing:

Feedforward Connections: Information flows from lower to higher areas, as described in the hierarchical model.
Feedback Connections: Higher areas send information back to lower areas, influencing their processing.
Lateral Connections: Neurons within the same cortical area are interconnected, allowing for local computations and feature integration.
Dorsal and Ventral Streams: Two main pathways process different aspects of visual information (the "where" and "what" pathways) in parallel.

This complex network of connections allows for rapid and efficient processing of visual information, enabling us to quickly recognize objects and understand scenes.

****Temporal Dynamics:****
The visual system processes information at multiple timescales:

Rapid Initial Response: The first wave of neural activity occurs within 100-150ms after stimulus onset.
Sustained Processing: Continued processing and refinement of visual representations over several hundred milliseconds.
Feedback and Recurrent Processing: Ongoing interactions between different brain areas can persist for seconds.

Understanding these temporal dynamics is crucial for accurately modeling the brain's response to visual stimuli.
Rationale for Using CNNs and GNNs
Given the complex nature of the visual system, our model architecture combines CNNs and GNNs to capture different aspects of visual processing in the brain.
Convolutional Neural Networks (CNNs)
We use a Modified ResNet as our visual feature extractor, leveraging the power of CNNs for several reasons:

Hierarchical Feature Extraction: CNNs naturally model the hierarchical processing of the visual cortex. Lower layers detect simple features (e.g., edges), while higher layers combine these to represent more complex patterns.
Translation Invariance: The use of shared weights in CNNs mirrors the brain's ability to recognize objects regardless of their position in the visual field.
Local Connectivity: Convolutional layers process local regions of the input, similar to how neurons in the visual cortex have localized receptive fields.
Parameter Efficiency: Weight sharing in CNNs reduces the number of parameters, making the model more efficient and less prone to overfitting.

Graph Neural Networks (GNNs)
Our Multi-Layer Cortical Network uses graph convolutions to model the brain's complex interconnectivity:

Non-Euclidean Data Structure: The brain's connectivity doesn't follow a regular grid-like structure. GNNs can naturally represent and process data on irregular domains.
Modeling Brain Connectivity: The learnable adjacency matrix in our GNN allows the model to discover and leverage the underlying connectivity patterns in the brain.
Integrating Spatial and Temporal Information: Graph convolutions can capture both spatial relationships between brain regions and temporal dynamics of neural activity.
Flexibility: GNNs can adapt to different brain structures and connectivity patterns, potentially allowing for subject-specific modeling.
Multi-scale Processing: The multi-layer structure of our GNN, combined with inter-layer connections, allows for processing at multiple spatial and temporal scales, mirroring the brain's ability to integrate information across different levels of abstraction.

*******************Future Directions:*******************
In addition to the previously mentioned future directions, we can consider the following avenues for research based on our understanding of the visual system:

Incorporating Attention Mechanisms: Implement attention modules that mimic the selective processing capabilities of the visual cortex, potentially improving the model's ability to focus on relevant features.

*Modeling Feedback Connections: Extend the GNN architecture to include explicit feedback connections, allowing information to flow from higher to lower layers, similar to the feedback processes in the brain.

*Multi-modal Integration: Develop models that can process and integrate information from multiple sensory modalities, reflecting the brain's ability to combine visual information with other senses.

*Adaptive Time Scales: Implement mechanisms that allow the model to process information at different time scales adaptively, potentially capturing both rapid initial responses and more sustained processing.

*Interpretability and Visualization: Develop techniques to visualize and interpret the learned representations and connectivity patterns, providing insights into how the model processes visual information.

*Real-time Processing: Optimize the model for real-time ECoG signal reconstruction, paving the way for potential brain-computer interface applications.

*Incorporating Neuroscientific Constraints: Introduce biologically-inspired constraints or priors into the model architecture or training process to ensure more neuroscientifically plausible representations and computations.

By pursuing these directions, we can continue to refine our model, making it not only more accurate in reconstructing ECoG signals but also more informative about the underlying neural processes involved in visual perception.
This project represents a significant step towards understanding and reconstructing neural responses to visual stimuli, with potential applications in neuroscience research, medical diagnostics, and brain-computer interfaces. By combining insights from neuroscience with advanced deep learning techniques, we aim to push the boundaries of our understanding of the human visual system and pave the way for innovative applications in healthcare and technology.
