# Prompts utilizados para crear el Pipeline en GitHub Actions

## Prompt para Tests de Backend
"Como Senior DevOps, crea un job en GitHub Actions para ejecutar los tests del backend. El backend es Node.js con TypeScript, usa Jest para tests, y el comando es 'npm test' en el directorio backend/. Incluye checkout del código, setup de Node.js 18, instalación de dependencias y ejecución de tests."

## Prompt para Build de Backend
"Genera un job en GitHub Actions que dependa del job de tests, para hacer build del backend. Usa 'npm run build' que compila TypeScript. Sube los artifacts de dist/ para usar en deploy."

## Prompt para Deploy en EC2
"Crea un job de deploy que corra solo en push a main. Configura credenciales AWS con aws-actions/configure-aws-credentials. Crea un script de deploy que instale Node.js 18, PM2, PostgreSQL en EC2 si no están. Configura la DB con usuario y password de secrets. Copia el build, instala dependencias de prod, genera Prisma client, corre migraciones, y start la app con PM2 en puerto 8080. Usa scp y ssh para transferir y ejecutar el script en EC2."

## Prompt para Configuración de Secrets
"Lista los secrets necesarios en GitHub para el pipeline: EC2_INSTANCE (IP de EC2), AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY para credenciales AWS, DB_USER, DB_PASSWORD, DB_NAME, DB_PORT para PostgreSQL."

## Prompt para Generar Tests del Backend
"Como desarrollador, crea tests unitarios para el backend Node.js/TypeScript usando Jest. Para cada servicio (candidateService, positionService) y controlador (candidateController, positionController), crea archivos .test.ts que mockeen Prisma Client. Incluye tests para funciones principales como updateCandidateStage, getCandidatesByPositionService, y controladores de API. Usa jest.mock para simular @prisma/client y verifica que las funciones retornen los datos esperados."
