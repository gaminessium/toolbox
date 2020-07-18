# cargo 1.45.0 (744bd1fbb 2020-06-15)
# rustc 1.45.0 (5c1f21c3b 2020-07-13)

FROM rust:slim

ARG project_dir=/var/project​

RUN mkdir ${project_dir}
WORKDIR ${project_dir}

CMD [ "rustc", "--version" ]

# docker run --rm -ti rust rustc --version
# docker run --rm -ti rust cargo --version

# docker run --rm -ti -v $(pwd):/var/rust -u $(id -u $USER):$(id -g $USER) -e USER=$USER -w /var/rust rust cargo new sample
# docker run --rm -ti -v $(pwd):/var/rust -u $(id -u $USER):$(id -g $USER) -e USER=$USER -w /var/rust rust cargo run sample
