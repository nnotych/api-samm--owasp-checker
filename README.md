# demochecker

**demochecker** is a learning tool for automated REST API verification.  
It consists of two main parts:
- **Lab7** — a test API used as a playground for validation.
- **Demochecker** — a Python script with Docker infrastructure that runs checks against the API using configuration files and an OpenAPI specification.

---

## 📂 Project Structure

- **`lab7/`** — test API service:
  - contains code for a simple REST API with several endpoints,
  - used as the target for validation.
- **`check_api.py`** — main Python script:
  - executes HTTP requests,
  - verifies status codes,
  - compares responses with expected results,
  - validates against the OpenAPI specification.
- **`openapi.yaml`** — OpenAPI description of the API.
- **`api_qi.json` / `matrix.json`** — configuration files with test scenarios.
- **`requirements.txt`** — Python dependencies.
- **`Dockerfile`** — instructions to build a container image.
- **`docker-compose.yml`** — configuration to run the container.

---

## ⚙️ What It Checks

1. **API availability** — whether endpoints respond.  
2. **Status codes** — validation of expected results (`200`, `404`, `500`).  
3. **Response content** — comparison of JSON structure and values with test scenarios.  
4. **OpenAPI compliance** — endpoints match the specification in `openapi.yaml`.  
5. **Docker stability** — API behaves consistently inside a container.

These checks align with **Verification practices** in the OWASP SAMM model (*Security Testing*, *Architecture Assessment*).

---

## 🚀 Running the Project

### Locally
```bash
pip install -r requirements.txt
python check_api.py
