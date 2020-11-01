# -*- coding: utf-8 -*-
# Copyright 2010-2020, Google Inc.
# All rights reserved.
#
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions are
# met:
#
#     * Redistributions of source code must retain the above copyright
# notice, this list of conditions and the following disclaimer.
#     * Redistributions in binary form must reproduce the above
# copyright notice, this list of conditions and the following disclaimer
# in the documentation and/or other materials provided with the
# distribution.
#     * Neither the name of Google Inc. nor the names of its
# contributors may be used to endorse or promote products derived from
# this software without specific prior written permission.
#
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
# "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
# LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
# A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
# OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
# SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
# LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
# DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
# THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
# (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
# OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

# Visibility:  please choose a more appropriate default for the package,
# and update any rules that should be different.

load(
    "//:build_defs.bzl",
    "cc_binary_mozc",
    "cc_library_mozc",
    "cc_test_mozc",
)

cc_binary_mozc(
    name = "mozc_emacs_helper",
    srcs = ["mozc_emacs_helper.cc"],
    copts = [
        "$(STACK_FRAME_UNLIMITED)",  # mozc_emacs_helper.cc
    ],
    visibility = ["//:__subpackages__"],
    deps = [
        ":mozc_emacs_helper_lib",
        "//base",
        "//base:flags",
        "//base:init_mozc",
        "//base:logging",
        "//base:util",
        "//base:version",
        "//client",
        "//config:config_handler",
        "//ipc",
        "//protocol:commands_proto",
        "@com_google_absl//absl/strings:str_format",
    ],
)

cc_library_mozc(
    name = "mozc_emacs_helper_lib",
    srcs = [
        "client_pool.cc",
        "mozc_emacs_helper_lib.cc",
    ],
    hdrs = [
        "client_pool.h",
        "mozc_emacs_helper_lib.h",
    ],
    deps = [
        "//base",
        "//base:logging",
        "//base:number_util",
        "//base:port",
        "//base:util",
        "//base/protobuf",
        "//base/protobuf:descriptor",
        "//base/protobuf:message",
        "//client",
        "//composer:key_parser",
        "//protocol:commands_proto",
        "//storage:lru_cache",
        "//storage:lru_storage",
        "@com_google_absl//absl/strings:str_format",
    ],
)

cc_test_mozc(
    name = "mozc_emacs_helper_lib_test",
    size = "small",
    srcs = ["mozc_emacs_helper_lib_test.cc"],
    deps = [
        ":mozc_emacs_helper_lib",
        "//base:util",
        "//base/protobuf:message",
        "//protocol:commands_proto",
        "//testing:gunit_main",
    ],
)
