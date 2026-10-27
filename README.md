# Voltrus device templates

Public catalog of device templates (`voltrus-device-template/1`) for [Voltrus SCADA](https://github.com/VoltrusID/voltrus-scada): Modbus register maps and BACnet object lists with scaling, units and field quirks.

Voltrus SCADA reads `index.json` from this repository by default (Device managers → Templates → Catalog, or `GET /api/v1/device-templates/catalog`), verifies each file's sha256 and stores the template locally.

## Contributing

1. Configure the device in Voltrus SCADA, check the values against the real hardware, then use **Save as template** (or `POST /api/v1/device-templates/from-device/{device_id}`) and export it.
2. Set `verified: true` only for maps checked on real hardware, and say what was checked in `verified_notes` (firmware, site, date).
3. Add the file and regenerate the index: `voltrus template catalog <this repo>`.
4. Open a pull request.

The format is documented in [docs/device-templates.md](https://github.com/VoltrusID/voltrus-scada/blob/main/docs/device-templates.md). The built-in templates seeded here come from the simulator profiles and are marked `verified: false`.

Templates are licensed CC-BY-4.0 unless a file says otherwise.
