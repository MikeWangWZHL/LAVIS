# ego4d_dynamic_modeling v1 dataset card

## Description
For each clip, we sample maximum `50` narration annotations. For each narration timestamp at frame `t`, we consider a 30 frame window, we extract the frame at `t-25` as the start state image, and the frame at `t+5` as the end state image.  

## Size
- train: 325817
- val: 40727
- test: 40728

## Annotation Json format
The annotation jsons in `annotations/` contains a dictionary where the key is the unique id of a narration text, the value is the text.
The key is constructed as follows:
`<clip_uid>__narration_pass_<narration_pass_index>__<narration_index>` for example: `ce351502-e824-4059-a41f-d55695938cda__narration_pass_2__35`

Note that the `<clip_uid>` is used for finding the corresponding image pair in `images/` dir

## Images dir format
The images in `images/` are the start and end state frames for each instance. The naming is constructed as follows:
`<clip_uid>__narration_pass_<narration_pass_index>__<narration_index>__<start/end>.jpg`