# Copyright 2019 The TensorFlow Probability Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
# ============================================================================
# Description:
#   Experimental methods and objectives for variational inference.

load(
    "//tensorflow_probability/python:build_defs.bzl",
    "multi_substrate_py_library",
    "multi_substrate_py_test",
)

licenses(["notice"])

package(
    default_visibility = [
        "//tensorflow_probability:__subpackages__",
    ],
)

multi_substrate_py_library(
    name = "vi",
    srcs = ["__init__.py"],
    deps = [
        ":automatic_structured_vi",
        ":surrogate_posteriors",
        "//tensorflow_probability/python/experimental/vi/util",
        "//tensorflow_probability/python/internal:all_util",
    ],
)

multi_substrate_py_library(
    name = "automatic_structured_vi",
    srcs = ["automatic_structured_vi.py"],
    deps = [
        # tensorflow dep,
        "//tensorflow_probability/python/bijectors:identity",
        "//tensorflow_probability/python/bijectors:restructure",
        "//tensorflow_probability/python/bijectors:scale",
        "//tensorflow_probability/python/bijectors:shift",
        "//tensorflow_probability/python/bijectors:sigmoid",
        "//tensorflow_probability/python/distributions:beta",
        "//tensorflow_probability/python/distributions:chi2",
        "//tensorflow_probability/python/distributions:exponential",
        "//tensorflow_probability/python/distributions:gamma",
        "//tensorflow_probability/python/distributions:half_normal",
        "//tensorflow_probability/python/distributions:independent",
        "//tensorflow_probability/python/distributions:joint_distribution_auto_batched",
        "//tensorflow_probability/python/distributions:joint_distribution_coroutine",
        "//tensorflow_probability/python/distributions:markov_chain",
        "//tensorflow_probability/python/distributions:sample",
        "//tensorflow_probability/python/distributions:transformed_distribution",
        "//tensorflow_probability/python/distributions:truncated_normal",
        "//tensorflow_probability/python/distributions:uniform",
        "//tensorflow_probability/python/experimental/util",
        "//tensorflow_probability/python/internal:distribution_util",
        "//tensorflow_probability/python/internal:dtype_util",
        "//tensorflow_probability/python/internal:prefer_static",
        "//tensorflow_probability/python/internal:samplers",
        "//tensorflow_probability/python/internal:trainable_state_util",
        "//tensorflow_probability/python/util",
    ],
)

multi_substrate_py_library(
    name = "surrogate_posteriors",
    srcs = ["surrogate_posteriors.py"],
    deps = [
        # tensorflow dep,
        "//tensorflow_probability/python/bijectors:chain",
        "//tensorflow_probability/python/bijectors:identity",
        "//tensorflow_probability/python/bijectors:invert",
        "//tensorflow_probability/python/bijectors:joint_map",
        "//tensorflow_probability/python/bijectors:reshape",
        "//tensorflow_probability/python/bijectors:restructure",
        "//tensorflow_probability/python/bijectors:scale_matvec_linear_operator",
        "//tensorflow_probability/python/bijectors:shift",
        "//tensorflow_probability/python/bijectors:softplus",
        "//tensorflow_probability/python/bijectors:split",
        "//tensorflow_probability/python/distributions:independent",
        "//tensorflow_probability/python/distributions:joint_distribution_util",
        "//tensorflow_probability/python/distributions:normal",
        "//tensorflow_probability/python/distributions:sample",
        "//tensorflow_probability/python/distributions:transformed_distribution",
        "//tensorflow_probability/python/experimental/util",
        "//tensorflow_probability/python/internal:dtype_util",
        "//tensorflow_probability/python/internal:prefer_static",
        "//tensorflow_probability/python/internal:samplers",
        "//tensorflow_probability/python/util",
    ],
)

multi_substrate_py_test(
    name = "automatic_structured_vi_test",
    size = "large",
    srcs = ["automatic_structured_vi_test.py"],
    numpy_tags = ["notap"],
    shard_count = 12,
    deps = [
        ":automatic_structured_vi",
        # absl/testing:parameterized dep,
        # numpy dep,
        # optax dep,
        # tensorflow dep,
        "//tensorflow_probability/python/bijectors:sigmoid",
        "//tensorflow_probability/python/bijectors:softplus",
        "//tensorflow_probability/python/bijectors:square",
        "//tensorflow_probability/python/distributions:bernoulli",
        "//tensorflow_probability/python/distributions:beta",
        "//tensorflow_probability/python/distributions:cauchy",
        "//tensorflow_probability/python/distributions:chi2",
        "//tensorflow_probability/python/distributions:exponential",
        "//tensorflow_probability/python/distributions:gamma",
        "//tensorflow_probability/python/distributions:half_cauchy",
        "//tensorflow_probability/python/distributions:half_normal",
        "//tensorflow_probability/python/distributions:independent",
        "//tensorflow_probability/python/distributions:joint_distribution_auto_batched",
        "//tensorflow_probability/python/distributions:joint_distribution_named",
        "//tensorflow_probability/python/distributions:joint_distribution_sequential",
        "//tensorflow_probability/python/distributions:laplace",
        "//tensorflow_probability/python/distributions:markov_chain",
        "//tensorflow_probability/python/distributions:normal",
        "//tensorflow_probability/python/distributions:sample",
        "//tensorflow_probability/python/distributions:student_t",
        "//tensorflow_probability/python/distributions:transformed_distribution",
        "//tensorflow_probability/python/distributions:truncated_normal",
        "//tensorflow_probability/python/distributions:uniform",
        "//tensorflow_probability/python/experimental/util",
        "//tensorflow_probability/python/internal:custom_gradient",
        "//tensorflow_probability/python/internal:samplers",
        "//tensorflow_probability/python/internal:test_util",
        "//tensorflow_probability/python/math:gradient",
        "//tensorflow_probability/python/math:minimize",
        "//tensorflow_probability/python/vi:optimization",
    ],
)

multi_substrate_py_test(
    name = "surrogate_posteriors_test",
    size = "large",
    srcs = ["surrogate_posteriors_test.py"],
    numpy_tags = ["notap"],
    shard_count = 4,
    deps = [
        ":surrogate_posteriors",
        # absl/testing:parameterized dep,
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability/python/bijectors:exp",
        "//tensorflow_probability/python/bijectors:fill_triangular",
        "//tensorflow_probability/python/bijectors:identity",
        "//tensorflow_probability/python/bijectors:joint_map",
        "//tensorflow_probability/python/bijectors:masked_autoregressive",
        "//tensorflow_probability/python/bijectors:sigmoid",
        "//tensorflow_probability/python/bijectors:softplus",
        "//tensorflow_probability/python/distributions:deterministic",
        "//tensorflow_probability/python/distributions:exponential",
        "//tensorflow_probability/python/distributions:gamma",
        "//tensorflow_probability/python/distributions:independent",
        "//tensorflow_probability/python/distributions:joint_distribution_auto_batched",
        "//tensorflow_probability/python/distributions:joint_distribution_coroutine",
        "//tensorflow_probability/python/distributions:joint_distribution_named",
        "//tensorflow_probability/python/distributions:joint_distribution_sequential",
        "//tensorflow_probability/python/distributions:laplace",
        "//tensorflow_probability/python/distributions:logistic",
        "//tensorflow_probability/python/distributions:normal",
        "//tensorflow_probability/python/distributions:sample",
        "//tensorflow_probability/python/distributions:student_t",
        "//tensorflow_probability/python/experimental/vi/util",
        "//tensorflow_probability/python/internal:test_util",
        "//tensorflow_probability/python/vi:optimization",
    ],
)
