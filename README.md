# analizador-velas

Velas M1 de EURUSD, GBPUSD y AUDCAD. Solo datos de mercado: ni cuentas, ni operaciones, ni claves.

`<PAR>/m1/AAAA-MM-DD.parquet`: un archivo por par y día UTC (zstd), una fila por minuto cerrado.

| Columna | Qué es |
|---|---|
| `time` | inicio del minuto, segundos UTC |
| `open`, `high`, `low`, `close`, `volume`, `spread` | Dukascopy: precio medio, volumen de ticks y spread |
| `mt5_open` … `mt5_volume` | vela de un terminal MT5 (bid) cuando la había; si no, vacías |

Se actualizan una vez por hora (un commit por día: el de la hora siguiente sustituye al anterior).
