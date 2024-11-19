<header>
      <h1>Actividad Java Alura - Capacitación Oracle</h1>
  </header>

  <section>
      <h2>Descripción del Proyecto</h2>
      <p>Este proyecto corresponde a una actividad dentro del programa de capacitación en Java de Oracle, en colaboración con Alura. El objetivo es aprender a implementar aplicaciones Java utilizando buenas prácticas, así como integrar servicios web a través de APIs.</p>
      <p>En este ejercicio, se utiliza Java para desarrollar una aplicación que consume una API, realiza operaciones sobre datos y presenta resultados de manera adecuada. El proyecto forma parte del aprendizaje práctico en el contexto del curso de Java avanzado de Oracle.</p>
  </section>

  <section>
      <h2>Objetivos del Proyecto</h2>
      <ul>
          <li>Desarrollar habilidades prácticas en programación Java.</li>
          <li>Aprender a consumir APIs RESTful desde una aplicación Java.</li>
          <li>Trabajar con datos JSON utilizando bibliotecas como <strong>Gson</strong> o <strong>Jackson</strong>.</li>
          <li>Implementar buenas prácticas de programación orientada a objetos en Java.</li>
          <li>Familiarizarse con el manejo de excepciones y la integración de servicios web externos.</li>
      </ul>
  </section>

  <section>
      <h2>Tecnologías Utilizadas</h2>
      <ul>
          <li><strong>Java 8+</strong>: Lenguaje de programación para desarrollar la aplicación.</li>
          <li><strong>APIs RESTful</strong>: Para la integración con servicios web.</li>
          <li><strong>JSON</strong>: Para manejar los datos que se comunican entre el cliente y la API.</li>
          <li><strong>Gson</strong> o <strong>Jackson</strong>: Bibliotecas para procesar respuestas en formato JSON.</li>
          <li><strong>Maven</strong> o <strong>Gradle</strong>: Herramientas de construcción para gestionar dependencias y compilar el proyecto.</li>
      </ul>
  </section>

  <section>
      <h2>Instrucciones para Ejecutar el Proyecto</h2>
      <p>Sigue estos pasos para ejecutar el proyecto en tu máquina local:</p>
      <ol>
          <li><strong>Clona el repositorio:</strong>
              <pre>git clone https://github.com/tu_usuario/actividadJavaAlura.git</pre>
          </li>
          <li><strong>Accede al directorio del proyecto:</strong>
              <pre>cd actividadJavaAlura</pre>
          </li>
          <li><strong>Compila y ejecuta el proyecto:</strong>
              <p>Si usas Maven o Gradle, asegúrate de tener estas herramientas instaladas. Luego, ejecuta los siguientes comandos:</p>
              <pre>mvn clean install</pre>
              <pre>mvn exec:java</pre>
          </li>
          <p>Si usas un IDE como IntelliJ IDEA o Eclipse, simplemente abre el proyecto y ejecútalo desde el IDE.</p>
      </ol>
  </section>

  <section>
      <h2>Ejemplo de Código</h2>
      <p>A continuación se muestra un ejemplo básico de cómo consumir una API desde una aplicación Java utilizando <strong>HttpClient</strong> (disponible a partir de Java 11):</p>
      <pre>
import java.net.URI;
import java.net.http.HttpClient;
import java.net.http.HttpRequest;
import java.net.http.HttpResponse;
import com.google.gson.Gson;

public class ApiClient {
  public static void main(String[] args) {
      try {
          // Crear cliente HTTP
          HttpClient client = HttpClient.newHttpClient();

          // Realizar solicitud GET a la API
          HttpRequest request = HttpRequest.newBuilder()
                  .uri(new URI("https://api.example.com/data"))
                  .build();

          // Enviar solicitud y recibir respuesta
          HttpResponse<String> response = client.send(request, HttpResponse.BodyHandlers.ofString());

          // Parsear la respuesta JSON
          Gson gson = new Gson();
          ApiResponse apiResponse = gson.fromJson(response.body(), ApiResponse.class);

          // Mostrar los datos recibidos
          System.out.println("Datos recibidos: " + apiResponse.getData());

      } catch (Exception e) {
          e.printStackTrace();
      }
  }
}

class ApiResponse {
  private String data;

  public String getData() {
      return data;
  }
}
      </pre>
      <p>En este ejemplo, se hace una solicitud HTTP GET a una API, y luego se parsea la respuesta JSON utilizando Gson. La respuesta contiene una propiedad "data" que se muestra en la consola.</p>
  </section>

  <section>
      <h2>Contribuciones</h2>
      <p>Si deseas contribuir al proyecto, puedes seguir estos pasos:</p>
      <ol>
          <li><strong>Haz un fork del repositorio:</strong> Crea una copia del proyecto para realizar cambios en tu propio repositorio.</li>
          <li><strong>Crea una nueva rama:</strong> Asegúrate de crear una nueva rama para agregar características o corregir errores.
              <pre>git checkout -b feature/nueva-funcionalidad</pre>
          </li>
          <li><strong>Realiza los cambios:</strong> Haz los cambios necesarios y asegúrate de que todo funcione correctamente.</li>
          <li><strong>Haz commit de tus cambios:</strong>
              <pre>git commit -m "Descripción de los cambios realizados"</pre>
          </li>
          <li><strong>Sube tus cambios:</strong>
              <pre>git push origin feature/nueva-funcionalidad</pre>
          </li>
          <li><strong>Abre un pull request:</strong> Cuando hayas subido tus cambios, abre un pull request para revisar y fusionar los cambios con la rama principal.</li>
      </ol>
  </section>

  <section>
      <h2>Licencia</h2>
      <p>Este proyecto está bajo la licencia <strong>MIT</strong>. Puedes ver los detalles completos en el archivo <code>LICENSE</code>.</p>
  </section>

  <section>
      <h2>Agradecimientos</h2>
      <p>Agradecemos a Oracle, Alura y todos los colaboradores que contribuyen a este programa de capacitación.</p>
  </section>

</body>
</html>
