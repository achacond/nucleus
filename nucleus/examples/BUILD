# Example programs for demonstrating Nucleus's APIs.
# load("//devtools/python/blaze:python3.bzl", "py2and3_test")
# KEEP THIS LINE to import nucleus.bzl externally

package(
    default_visibility = [
        "//visibility:public",
    ],
)

licenses(["notice"])  # Apache License 2.0

exports_files(["LICENSE"])

py_library(
    name = "examples_py",
    deps = [
        ":add_ad_to_vcf",
        ":apply_genotyping_prior",
        ":ascii_pileup",
        ":count_variants",
        ":filter_vcf",
        ":ngs_errors",
        ":validate_vcf",
    ],
)

py_binary(
    name = "add_ad_to_vcf",
    srcs = ["add_ad_to_vcf.py"],
    deps = [
        "//nucleus/io:vcf",
        "//nucleus/util:variant_utils",
        "//nucleus/util:variantcall_utils",
        "//nucleus/util:vcf_constants",
        "@absl_py//absl:app",
    ],
)

py_test(
    name = "add_ad_to_vcf_test",
    size = "small",
    srcs = ["add_ad_to_vcf_test.py"],
    data = [
        "//nucleus/testdata",
    ],
    srcs_version = "PY2AND3",
    deps = [
        ":add_ad_to_vcf",
        "//nucleus/io:vcf",
        "//nucleus/testing:py_test_utils",
        "@absl_py//absl/testing:absltest",
    ],
)

py_binary(
    name = "ascii_pileup",
    srcs = ["ascii_pileup.py"],
    deps = [
        "//nucleus/io:sam",
        "//nucleus/util:ranges",
        "@absl_py//absl:app",
    ],
)

py_binary(
    name = "count_variants",
    srcs = ["count_variants.py"],
    deps = [
        "//nucleus/io:vcf",
        "//nucleus/util:variant_utils",
        "@absl_py//absl:app",
    ],
)

py_test(
    name = "count_variants_test",
    size = "small",
    srcs = ["count_variants_test.py"],
    data = [
        "//nucleus/testdata",
    ],
    deps = [
        ":count_variants",
        "//nucleus/testing:py_test_utils",
        "@absl_py//absl/testing:absltest",
    ],
)

py_binary(
    name = "filter_vcf",
    srcs = ["filter_vcf.py"],
    deps = [
        "//nucleus/io:vcf",
        "@absl_py//absl:app",
    ],
)

py_test(
    name = "filter_vcf_test",
    size = "small",
    srcs = ["filter_vcf_test.py"],
    data = [
        "//nucleus/testdata",
    ],
    deps = [
        ":filter_vcf",
        "//nucleus/io:vcf",
        "//nucleus/testing:py_test_utils",
        "@absl_py//absl/testing:absltest",
    ],
)

py_binary(
    name = "validate_vcf",
    srcs = ["validate_vcf.py"],
    deps = [
        "//nucleus/io:fasta",
        "//nucleus/io:vcf",
        "//nucleus/util:variant_utils",
        "@absl_py//absl:app",
    ],
)

py_test(
    name = "validate_vcf_test",
    size = "small",
    srcs = ["validate_vcf_test.py"],
    data = [
        "//nucleus/testdata",
    ],
    deps = [
        ":validate_vcf",
        "//nucleus/protos:reference_py_pb2",
        "//nucleus/protos:variants_py_pb2",
        "//nucleus/testing:py_test_utils",
        "@absl_py//absl/testing:absltest",
    ],
)

py_binary(
    name = "ngs_errors",
    srcs = ["ngs_errors.py"],
    deps = [
        "//nucleus/io:fasta",
        "//nucleus/io:genomics_writer",
        "//nucleus/io:sam",
        "//nucleus/io:vcf",
        "//nucleus/protos:reads_py_pb2",
        "//nucleus/util:cigar",
        "//nucleus/util:py_utils",
        "//nucleus/util:ranges",
        "//nucleus/util:variant_utils",
        "@absl_py//absl:app",
        "@org_tensorflow//tensorflow:tensorflow_py",
    ],
)

py_test(
    name = "ngs_errors_test",
    size = "small",
    srcs = ["ngs_errors_test.py"],
    data = ["//nucleus/testdata"],
    srcs_version = "PY2AND3",
    deps = [
        ":ngs_errors",
        "//nucleus/io:genomics_reader",
        "//nucleus/testing:py_test_utils",
        "@absl_py//absl/testing:absltest",
        "@org_tensorflow//tensorflow:tensorflow_py",
    ],
)

py_binary(
    name = "apply_genotyping_prior",
    srcs = ["apply_genotyping_prior.py"],
    deps = [
        "//nucleus/io:vcf",
        "//nucleus/util:variant_utils",
        "//nucleus/util:variantcall_utils",
        "@absl_py//absl:app",
    ],
)

py_test(
    name = "apply_genotyping_prior_test",
    size = "small",
    srcs = ["apply_genotyping_prior_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":apply_genotyping_prior",
        "//nucleus/protos:variants_py_pb2",
        "@absl_py//absl/testing:absltest",
    ],
)
