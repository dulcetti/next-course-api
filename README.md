# next-course-api

An API example based on Next.js course with Strapi

## Clear database

docker exec -i next-course-api_postgres_1 psql -U strapi -d postgres -c "SELECT pg_terminate_backend(pid) FROM pg_stat_activity WHERE pid <> pg_backend_pid() AND datname = 'strapi';"
docker exec -i next-course-api_postgres_1 psql -U strapi -d postgres -c "DROP DATABASE strapi;"
docker exec -i next-course-api_postgres_1 psql -U strapi -d postgres -c "REVOKE CONNECT ON DATABASE strapi FROM PUBLIC, strapi;"

## Database Importation

cat strapi.sql | docker exec -i CONTAINER_NAME psql -U USERNAME -d DATABASE_NAME

## Database Exportation

docker exec -i CONTAINER*NAME pg_dump --username USERNAME --password DATABASE_NAME > DUMP*`date +%d-%m-%Y"_"%H_%M_%S`.sql
