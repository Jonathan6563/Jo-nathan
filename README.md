import openai
import requests

# Substitua pela sua chave de API da OpenAI
openai.api_key = "sua_chave_api_aqui"

# Descrição sensual, mas respeitosa e artística
prompt = (
    "Uma mulher morena com curvas acentuadas, nua em um ambiente sofisticado, "
    "com iluminação suave e pose sensual. Ela tem cabelos escuros liso, pele bronzeada e expressão confiante. "
    "Estilo: arte digital realista, com atmosfera suave e foco na beleza estética."
)

response = openai.Image.create(
    prompt=prompt,
    n=1,
    size="1024x1024"
)

# URL da imagem gerada
image_url = response['data'][0]['url']
print("Imagem gerada:", image_url)

# (Opcional) Baixar a imagem
image_data = requests.get(image_url).content
with open("modelo_morena_sensual.png", "wb") as f:
    f.write(image_data)

print("Imagem salva como modelo_morena_sensual.png")
