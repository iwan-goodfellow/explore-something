# image dockernya
FROM --platform=linux/amd64 node:11.15

FROM python:3.9.1

# running instalasi library pandas di image ini
RUN pip install pandas

# ngatur dir kerja dalam container
WORKDIR /app

# nyalin skrip ke container. parameter pertama adl file sumber, parameter kedua adl tujuan
COPY pipeline.py pipeline.pys

# define apa yg dilakukan pertama kali saat kontainer di run
# dalam contoh kita akan jalannin script pipeline.py
ENTRYPOINT [ "python",'pipeline.py' ]


docker run -it ^
    -e POSTGRES_USER="root" ^
    -e POSTGRES_PASSWORD="root" ^
    -e POSTGRES_DB="ny_taxi" ^
    -v "/d/003-belajarSWE/explore-something/materi-1/ny_taxi_postgres_data:/var/lib/postgresql/data" ^
    -p 5432:5432 ^
    postgres:13