#!/usr/bin/env bash
# -*- coding: utf-8 -*-
# shellcheck shell=bash disable=SC1091,SC2039,SC2166
#
# /usr/share/libalpm/scripts/big-update-bigapps-category-in-desktopfiles
# Created: 2024/11/12 - 20:46
# Altered: 2024/11/12 - 20:46
#
# Copyright (c) 2024-2024, Vilmar Catafesta <vcatafesta@gmail.com>
# All rights reserved.

: <<'REMARK'
Esse comando percorre todos os arquivos .desktop no diretório /usr/share/applications/
que começam com big, e realiza a seguinte ação:
Substitui todas as ocorrências de Biglinux por Big Apps.
Adiciona Big Apps ao final da linha, caso ainda não esteja presente.

Exemplo: Se a linha original for: Categories=Utility;Biglinux;Graphics;
Ela será transformada em:         Categories=Utility;Big Apps;Graphics;

Se a linha original for:  Categories=Utility;Graphics;
Ela será transformada em: Categories=Utility;Graphics;Big Apps;
REMARK

for i in /usr/share/applications/big*.desktop; do
    sed -i '/^Categories=/ {
        s/\bBiglinux\b/Big Apps/g
        /Big Apps/! s/$/;Big Apps/
    }' "$i"
done
