import requests, csv

TOKEN = "TU_GITHUB_TOKEN"
HEADERS = { "Authorization": f"token {TOKEN}" }
paises = ["Argentina", "Bolivia", ..., "Venezuela"]

with open("latam_recruited.csv", "w", newline="") as f:
    writer = csv.writer(f)
    writer.writerow(["pais", "login", "url", "followers"])
    for pais in paises:
        for page in range(1, 6):  # ajusta pages si necesitas más
            params = {
                "q": f'location:"{pais}"',
                "per_page": 100,
                "page": page
            }
            res = requests.get("https://api.github.com/search/users",
                               headers=HEADERS, params=params)
            items = res.json().get("items", [])
            if not items: break
            for u in items:
                writer.writerow([pais, u["login"], u["html_url"], u["followers"]])
