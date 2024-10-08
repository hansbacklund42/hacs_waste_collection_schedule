# Technischer Betriebsdienst Reutlingen

Technischer Betriebsdienst Reutlingen is supported by the generic [ICS](/doc/source/ics.md) source. For all available configuration options, please refer to the source description.


## How to get the configuration arguments

- Go to <https://www.tbr-reutlingen.de/entsorgungskalender> and select your street.  
- Right-click on `Abfuhrtermine (iCal) herunterladen` and copy link address.
- Replace the `url` in the example configuration with this link.
- The trailing part of the URL is a URL-encoded JSON string. It contains the "from" and "to" dates for the calendar. You need to replace the "from" date with `01.01.{%Y}` and the "to" date with `31.12.{%Y}`. You can use a ureldecoding/-encoding service to make the URL path easier to edit.

## Examples

### Reutlingen

```yaml
waste_collection_schedule:
  sources:
    - name: ics
      args:
        url: https://www.tbr-reutlingen.de/tools/garbageCalendar/ics/1/%7B%22garbageTypeFilter%22%3A%7B%22RM2%22%3A%22RM2%22%2C%22RM4%22%3A%22RM4%22%2C%22BIO%22%3A%22BIO%22%2C%22GES%22%3A%22GES%22%2C%22GRG%22%3A%22GRG%22%2C%22PAP%22%3A%22PAP%22%2C%22WST%22%3A%22WST%22%7D%2C%22dateFilter%22%3A%7B%22from%22%3A%2201.01.{%Y}%22%2C%22to%22%3A%2231.12.{%Y}%22%7D%7D
```
