# rustc 1.42.0 (b8cedc004 2020-03-09)
# cargo 1.42.0 (86334295e 2020-01-31)

FROM rust:1.31

ARG project_dir=/var/project​

RUN mkdir ${project_dir}
WORKDIR ${project_dir}

CMD [ "rustc", "--version" ]

# docker run --rm -ti rust rustc --version
# docker run --rm -ti rust cargo --version

# docker run --rm -ti -v $(pwd):/var/rust -u $(id -u $USER):$(id -g $USER) -e USER=$USER -w /var/rust rust cargo new sample
# docker run --rm -ti -v $(pwd):/var/rust -u $(id -u $USER):$(id -g $USER) -e USER=$USER -w /var/rust rust cargo run sample
