## LLMs - GPUs / Memory required

### We have 40G and 80G A100s on Sol. Specify the memory required (--mem=XXXG) and number of GPU resources required (gpu:a100:X) accordingly.
### If you want to reserve the entire node with max 4 GPUs, leave the number of cores field as blank.

1. LLaMa2-chat

You have to specify the path instead of model id in this case as shown below (the "/" in the end is important):

model_id = f"/scratch/dshah47/.cache/licensed_models/Llama2-70b-chat-hf/"
(Change the number of parameters in the name)

Approx memory required:

| #Parameters | Original Model | dtype=bfloat16 | load_in_8bits=True |
|-------------|----------------|----------------|--------------------|
| 7b          | 26G            | 13G            | 7G                 |
| 13b         | 49G            | 24G            | 13G                |
| 70b         | 257G           | 128G           | 67G                |

2. Falcon / Falcon-instruct

model_id = "tiiuae/falcon-7b" or 
model_id = "tiiuae/falcon-7b-instruct"
(Change the number of parameters in the name)

Approx memory required:

| #Parameters | Original Model | dtype=bfloat16 | load_in_8bits=True |
|-------------|----------------|----------------|--------------------|
| 7b          | 25G            | 13G            | 8G                 |
| 40b         | 156G           | 78G            | 42G                |

3. StableBeluga2

model_id = "stabilityai/StableBeluga2"

Approx memory required:

| #Parameters | Original Model | dtype=bfloat16 | load_in_8bits=True |
|-------------|----------------|----------------|--------------------|
| 70b         | 257G           | 128G           | 66G                |

4. MPT / MPT-chat / MPT-instruct

model_id = 'mosaicml/mpt-30b-instruct' or
model_id = 'mosaicml/mpt-30b-chat' or 
model_id = 'mosaicml/mpt-30b'

Approx memory required:

| #Parameters | Original Model | dtype=bfloat16 | load_in_8bits=True |
|-------------|----------------|----------------|--------------------|
| 30b         | 111G           | 55G            | 30G                |

5. CodeLlama / CodeLlama-Python / CodeLlama-instruct

model_id = "codellama/CodeLlama-7b-hf" or 
model_id = "codellama/CodeLlama-7b-Python-hf" or
model_id = "codellama/CodeLlama-7b-instruct-hf"
(Change the number of parameters in the name)

Approx memory required:

| #Parameters | Original Model | dtype=bfloat16 | load_in_8bits=True |
|-------------|----------------|----------------|--------------------|
| 7b          | 26G            | 12G            | x                  |
| 13b         | 49G            | 25G            | x                  |
| 34b         | 126G           | 64G            | x                  |

6. falcon-180b / falcon-180b-chat

PLEASE READ THE LICENSE AND ACCEPTABLE USE POLICY BEFORE USING THE MODEL.
You have to specify the path instead of model id in this case as shown below (the "/" in the end is important):

model_id = "/scratch/dshah47/.cache/licensed_models/falcon-180B/" or 
model_id = "/scratch/dshah47/.cache/licensed_models/falcon-180B-chat/"

Approx memory required:

| #Parameters | Original Model    | dtype=bfloat16     | load_in_8bits=True| load_in_4bits=True |
|-------------|-------------------|--------------------|------------------ |--------------------|
| 180b        | 335G              | 298G               | 178G              | 119G               |
|             |(Not possible with |(Not possible with  |(Not possible with |                    |
|             |current h/w)       |current h/w)        |40G A100s)         |                    |