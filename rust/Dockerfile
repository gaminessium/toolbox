# cargo 1.45.0 (744bd1fbb 2020-06-15)
# rustc 1.45.0 (5c1f21c3b 2020-07-13)

FROM rust:slim

ARG project_dir=/var/rust

RUN mkdir -p ${project_dir}
WORKDIR ${project_dir}

CMD [ "rustc", "--version" ]
