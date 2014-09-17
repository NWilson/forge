# This fork of Forge

I have forked off Forge in order to package it for use as an emscripten library. A very simple C interface is exported, providing basic raw RSA encryption. A suitable padding method must be used (such as OAEP for encryption/decryption and PSS for sign/verify).

# API

    int rvutil_rsa_new();
    int rvutil_rsa_free(int descriptor);
    int rvutil_rsa_generate(int d, int size, int exponent);
    int rvutil_rsa_import_public(int d, const char* n, const char* e);
    int rvutil_rsa_import_private(int d, const char* n, const char* e,
                            const char* d, const char* p, const char* q,
                            const char* dmp1, const char* dmq1,
                            const char* iqmp);
    int rvutil_rsa_export(int d, const char* value, unsigned char* buffer,
                    size_t buffer_len);
    int rvutil_rsa_get_size(int d);
    int rvutil_rsa_crypt_raw(int d, int encrypt,
                       const unsigned char* data, size_t data_len,
                       unsigned char* buffer, size_t buffer_len);

# Forge

A native implementation of TLS (and various other cryptographic tools) in
JavaScript.

## Introduction

The Forge software is a fully native implementation of the TLS protocol in
JavaScript as well as a set of tools for developing Web Apps that utilize many
network resources.
