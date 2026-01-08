# TP Docker - RentalService

## Commandes réalisées (TP Docker)

### Clonage et configuration du dépôt

```bash
git clone <url_du_fork>
cd TP_1
git remote remove origin
git remote add origin https://github.com/m4tth1euNa0p1c/TP1-L3-XIN502-B3-IN-2025-2026.git
```

### Build et run sans Docker

```bash
cd RentalService

# Build avec Gradle (Windows)
.\gradlew.bat build

# Ou sur Linux/Mac
./gradlew build

# Lancer l'application
java -jar build/libs/RentalService-0.0.1-SNAPSHOT.jar

# Vérifier le endpoint
curl http://localhost:8080/bonjour
```

### Docker

```bash
cd RentalService

# Build de l'image Docker
docker build -t rentalservice-tp .

# Lancer le conteneur
docker run --rm -p 8080:8080 rentalservice-tp

# Vérifier le endpoint
curl http://localhost:8080/bonjour
```

### Docker Hub

**Image publiée** : `matthkernel/rentalservice-tp:latest`

```bash
# Connexion à Docker Hub
docker login

# Tag de l'image
docker tag rentalservice-tp matthkernel/rentalservice-tp:latest

# Push de l'image
docker push matthkernel/rentalservice-tp:latest

# Pull de l'image (depuis n'importe quelle machine)
docker pull matthkernel/rentalservice-tp:latest

# Run depuis Docker Hub
docker run --rm -p 8080:8080 matthkernel/rentalservice-tp:latest
```
