positional encoding 2D
* Somar
* concatenar
* usar 32 bandas - sin e cos. Fourier

random crop

4 patches - 1 -> total



pré-processamento dos patches com CNN

patches no início e no fim:
n_patch = 1, 2, 4, 8, 16, 196

seq_len = 128 + n_patch*2


loss_bar fazer média 


1, 2, 4 patches -> baselline e com CNN



Experiências:
* CLIP embedding - This is the baseline. The sequence in the decoder starts with the image embedding from CLIP, and autoregressively generates text to predict the caption for the image;
* Single patch embedding - Experimenting with less information and without using an embedding from a pre-trained image encoder;
* Patch at the beginning and at the end with mask - Train the model to do image-to-text and text-to-image tasks within the decoder. Should help to generalize and
* CNN pre-processing of the patches - Capture more information from the image into the patches;
* Multiple patches - Introducing some more information, but still with a lot of occlusion;
* 2D Fourier PE - Provides patches' PE, helping both image-to-text and text-to-image tasks;
* In inference, generate *n* patches sub-sequences and select the one with highest probability - Reduces the randomness of the generated captions due to the patch selection.









Inferência:
* Sub conjuntos de patches para cada GT -> escolher frase mais provável

\[IMAGE] \[IMAGE] caption1
\[IMAGE] \[IMAGE] caption2
\[IMAGE] \[IMAGE] caption3
\[IMAGE] \[IMAGE] caption4
\[IMAGE] \[IMAGE] caption5

Treino:
* Gerar 5 sub conjuntos para cada GT caption em cada epoch


Buscar pesos com:
* gradcam
* peso da 1ª layer attention