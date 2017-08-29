

``TODO``

## Порядок полей у Model

### Новая модель
* _name
* _description (обязательный!)
* _inherit (возможный)
* _inherits (возможный)
* _order (возможный)
* _rec_name (возможный)

### Расширение модели
* _inherit

## Python

* У related полей всегда ставить readonly=True. Кроме случает исключений, когда это действительно надо

## XML спецификация

* элемент ``record``, порядок атрибутов
   * model
   * id

* элемент ``field``, порядок атрибутов
   * name
   * или eval, или ref, или type

* элемент ``notebook``, порядок атрибутов
   * name
   * string

