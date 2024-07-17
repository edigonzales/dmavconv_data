# dmavconv_data

Testdatensatz importieren:
```
java -jar /Users/stefan/apps/ili2gpkg-5.1.0/ili2gpkg-5.1.0.jar --dbfile dmav_alles.gpkg --defaultSrsCode 2056 --nameByTopic --disableValidation --createBasketCol --createFk --createFkIdx --models "DMAV_Bodenbedeckung_V1_0;DMAV_DauerndeBodenverschiebungen_V1_0;DMAV_Dienstbarkeitsgrenzen_V1_0;DMAV_Einzelobjekte_V1_0;DMAV_FixpunkteAVKategorie2_V1_0;DMAV_FixpunkteAVKategorie3_V1_0;DMAV_FixpunkteLV_V1_0;DMAV_Gebaeudeadressen_V1_0;DMAV_Grundstuecke_V1_0;DMAV_HoheitsgrenzenAV_V1_0;DMAV_HoheitsgrenzenLV_V1_0;DMAV_Nomenklatur_V1_0;DMAV_PLZ_Ortschaft_V1_0;DMAV_Rohrleitungen_V1_0;DMAV_Toleranzstufen_V1_0;DMAVSUP_UntereinheitGrundbuch_V1_0" --doSchemaImport --import DMAVTYM_Alles_V1_0.xtf
```

Test mit DMAV_empty (xtf manuell hergestellt):
```
java -jar /Users/stefan/apps/ili2gpkg-5.1.0/ili2gpkg-5.1.0.jar --dbfile dmav_empty.gpkg --defaultSrsCode 2056 --nameByTopic --disableValidation --createBasketCol --createFk --createFkIdx --models "DMAV_Bodenbedeckung_V1_0;DMAV_DauerndeBodenverschiebungen_V1_0;DMAV_Dienstbarkeitsgrenzen_V1_0;DMAV_Einzelobjekte_V1_0;DMAV_FixpunkteAVKategorie2_V1_0;DMAV_FixpunkteAVKategorie3_V1_0;DMAV_FixpunkteLV_V1_0;DMAV_Gebaeudeadressen_V1_0;DMAV_Grundstuecke_V1_0;DMAV_HoheitsgrenzenAV_V1_0;DMAV_HoheitsgrenzenLV_V1_0;DMAV_Nomenklatur_V1_0;DMAV_PLZ_Ortschaft_V1_0;DMAV_Rohrleitungen_V1_0;DMAV_Toleranzstufen_V1_0;DMAVSUP_UntereinheitGrundbuch_V1_0" --doSchemaImport --import DMAV_emtpy.xtf
```

Import DM01 (uiuiui, ili1 und ili2 Gemisch):
```
java -jar /Users/stefan/apps/ili2gpkg-5.1.0/ili2gpkg-5.1.0.jar --dbfile dmav_empty.gpkg --defaultSrsCode 2056 --nameByTopic --disableValidation --createBasketCol --createFk --createFkIdx --models DM01AVCH24LV95D --importschema
```


```
java -jar /Users/stefan/apps/ili2gpkg-5.1.0/ili2gpkg-5.1.0.jar --dbfile dmav_empty.gpkg --defaultSrsCode 2056 --nameByTopic --disableValidation --createBasketCol --createFk --createFkIdx --models DM01AVCH24LV95D --import 2544.ch.so.agi.av.dm01_ch.itf
```

Aaaah. Ich glaube am Ende würde es an der fehlenden Sequence in SQLite scheitern. Woher nehme ich diese bei Fällen, wo ich in Postgres nextval() mache? Ginge vielleicht mit RETURNING *. Aber ich habe auch kein autoincrement auf den Tabellen.