from flask import Flask, render_template_string, request

app = Flask(__name__)

# --- Datos simulados ---
productos = [
    {"id": 1, "nombre": "Poke Bowl Clásico", "precio": 6990, "descripcion": "Base de arroz, salmón, palta y sésamo."},
    {"id": 2, "nombre": "Poke Bowl Vegano", "precio": 6490, "descripcion": "Base de quinoa, tofu, edamame y palta."},
    {"id": 3, "nombre": "Poke Bowl Proteico", "precio": 7290, "descripcion": "Base de arroz integral, pollo grillado y brócoli."}
]

# --- Plantilla base HTML ---
base_html = """
{% macro layout(content) %}
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Poké Fresh</title>
<style>
body {
  font-family: Arial, sans-serif;
  margin: 0; padding: 0;
  background: #fafafa;
  color: #333;
}
header {
  background: #4dc0b5;
  color: white;
  padding: 10px 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
nav a {
  color: white;
  margin-left: 15px;
  text-decoration: none;
}
main { padding: 20px; text-align: center; }
.hero { padding: 50px; background: #e0f7f5; border-radius: 8px; }
.btn {
  background: #4dc0b5;
  color: white;
  padding: 8px 15px;
  border: none;
  border-radius: 5px;
  text-decoration: none;
  cursor: pointer;
}
.catalogo { display: flex; justify-content: center; gap: 20px; flex-wrap: wrap; }
.card {
  background: white;
  padding: 15px;
  width: 200px;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}
.card img {
  width: 100%;
  border-radius: 8px;
}
footer {
  background: #333; color: white;
  padding: 10px; margin-top: 30px;
}
input, textarea {
  width: 80%;
  margin: 8px 0;
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #ccc;
}
.estado {
  color: #4dc0b5;
  font-weight: bold;
}
</style>
</head>
<body>
<header>
  <h1>🥗 Poké Fresh</h1>
  <nav>
    <a href="/">Inicio</a>
    <a href="/catalogo">Catálogo</a>
    <a href="/seguimiento">Seguimiento</a>
    <a href="/contacto">Contacto</a>
  </nav>
</header>
<main>
  {{ content | safe }}
</main>
<footer>
  <p>© 2025 Poké Fresh · Bowls hawaianos personalizados</p>
</footer>
</body>
</html>
{% endmacro %}
"""

# --- Rutas ---
@app.route('/')
def inicio():
    content = """
    <section class='hero'>
      <h2>Comida rápida y saludable</h2>
      <p>Poké bowls personalizados, hechos con ingredientes frescos y naturales.</p>
      <a href='/catalogo' class='btn'>Explorar Catálogo</a>
    </section>
    """
    return render_template_string(base_html + "{{ layout(content) }}", content=content)

@app.route('/catalogo')
def catalogo():
    cards = ""
    for p in productos:
        cards += f"""
        <div class='card'>
          <img src='https://images.unsplash.com/photo-1553621042-f6e147245754?auto=format&fit=crop&w=400&q=60'>
          <h3>{p["nombre"]}</h3>
          <p>{p["descripcion"]}</p>
          <p><strong>${p["precio"]}</strong></p>
          <a href='/pedido/{p["id"]}' class='btn'>Ver Detalle</a>
        </div>
        """
    content = f"<h2>Catálogo de Poké Bowls</h2><div class='catalogo'>{cards}</div>"
    return render_template_string(base_html + "{{ layout(content) }}", content=content)

@app.route('/pedido/<int:id>')
def pedido(id):
    p = next((x for x in productos if x["id"] == id), None)
    if not p:
        content = "<p>Producto no encontrado.</p>"
    else:
        content = f"""
        <h2>{p["nombre"]}</h2>
        <img src='https://images.unsplash.com/photo-1553621042-f6e147245754?auto=format&fit=crop&w=600&q=60' style='width:300px;border-radius:8px;'>
        <p>{p["descripcion"]}</p>
        <p><strong>Precio: ${p["precio"]}</strong></p>
        <button class='btn'>Agregar al carrito</button>
        """
    return render_template_string(base_html + "{{ layout(content) }}", content=content)

@app.route('/contacto', methods=['GET', 'POST'])
def contacto():
    enviado = False
    if request.method == 'POST':
        nombre = request.form.get("nombre")
        correo = request.form.get("correo")
        mensaje = request.form.get("mensaje")
        print(f"Mensaje de {nombre} ({correo}): {mensaje}")
        enviado = True

    if enviado:
        content = "<p><strong>¡Gracias por tu mensaje! Te responderemos pronto 😊</strong></p>"
    else:
        content = """
        <h2>Contáctanos</h2>
        <form method='post'>
          <input type='text' name='nombre' placeholder='Tu nombre' required><br>
          <input type='email' name='correo' placeholder='Tu correo' required><br>
          <textarea name='mensaje' placeholder='Tu mensaje...' required></textarea><br>
          <button type='submit' class='btn'>Enviar</button>
        </form>
        """
    return render_template_string(base_html + "{{ layout(content) }}", content=content)

@app.route('/seguimiento', methods=['GET', 'POST'])
def seguimiento():
    pedido_id = None
    estado = None
    if request.method == 'POST':
        pedido_id = request.form.get("pedido_id")
        if pedido_id:
            estado = "En preparación 🥗" if int(pedido_id) % 2 == 0 else "Listo para retiro 🚴"

    form = """
    <h2>Seguimiento de Pedido</h2>
    <form method='post'>
      <input type='number' name='pedido_id' placeholder='Número de pedido' required>
      <button type='submit' class='btn'>Consultar</button>
    </form>
    """
    if pedido_id:
        form += f"""
        <div style='margin-top:20px;'>
          <p><strong>Pedido #{pedido_id}</strong></p>
          <p>Estado: <span class='estado'>{estado}</span></p>
        </div>
        """
    return render_template_string(base_html + "{{ layout(content) }}", content=form)

# --- Iniciar servidor ---
if __name__ == '__main__':
    app.run(debug=True)
