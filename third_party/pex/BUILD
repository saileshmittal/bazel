licenses(["notice"])

py_library(
    name = 'pex',
    srcs = glob(['**/*.py']),
    deps = [
        "//third_party/py/setuptools:pkg_resources",
    ],
    visibility = ["//third_party:__pkg__"],
)

py_binary(
    name = '_pex',
    srcs = ["_pex.py"],
    deps = [
        ":pex",
    ],
    visibility = ["//visibility:public"],
)
