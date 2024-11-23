# Desc
Test de arch `PKGBUILD` pour automatiquement télécharger et compilé le programme.
# Problèmes
1. Un problème de compilation *LTO*:
```
_deps/swiftcollections-build/Sources/OrderedCollections/libOrderedCollections.a(OrderedSet+ReserveCapacity.swift.o) : un greffon est nécessaire à la gestion d'objets lto
```
Réglé en désactivant l'option `lto` dans le `PKGBUILD`

2. Aucune installation par défaut, rajout d'une installation custom:
```bash
install -Dm755 "${srcdir}/hylo-build/Sources/hc" "${pkgdir}/usr/bin/hc" 
```

3. Lenteur extrême, ajout de compilation parallèle:
```
cmake --build "${srcdir}/hylo-build" --parallel 20
```
Pas sûr que cela fonctionne

