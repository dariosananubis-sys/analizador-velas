# analizador-velas

Velas M1 de EURUSD, GBPUSD y AUDCAD para el Analizador (https://analizador-publico.onrender.com).
Solo datos de mercado: ni cuentas, ni operaciones, ni claves.

Estructura: `<PAR>/m1/AAAA-MM-DD.parquet` (UTC, columnas time/open/high/low/close, fuente).
Las escribe el Mac de Darío y Render las lee al arrancar.
