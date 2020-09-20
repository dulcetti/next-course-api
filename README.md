# next-course-api

An API example based on Next.js course with Strapi

## Database Importation
cat strapi.sql | docker exec -i CONTAINER_NAME psql -U USERNAME -d DATABASE_NAME

## Database Exportation
docker exec -i CONTAINER_NAME pg_dump --username USERNAME --password DATABASE_NAME > DUMP_`date +%d-%m-%Y"_"%H_%M_%S`.sql
