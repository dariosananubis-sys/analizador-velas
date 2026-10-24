# analizador-velas

Velas M1 de EURUSD, GBPUSD y AUDCAD para el Analizador (https://analizador-publico.onrender.com).
Solo datos de mercado: ni cuentas, ni operaciones, ni claves.

`<PAR>/m1/AAAA-MM-DD.parquet`: un archivo por par y día UTC (zstd), una fila por minuto cerrado.

| Columna | Qué es |
|---|---|
| `time` | inicio del minuto, segundos UTC |
| `open`, `high`, `low`, `close`, `volume`, `spread` | Dukascopy: precio medio, volumen de ticks y spread (la serie que analiza la app) |
| `mt5_open` … `mt5_volume` | vela oficial de MT5 (bid de ActivTrades) si el Mac la tenía; si no, vacías |

Las escribe el Mac de Darío una vez por hora (un commit por día: el de la hora siguiente sustituye al
anterior) y Render las lee cuando calcula sin el Mac, antes de pedir lo que falte a Dukascopy.
