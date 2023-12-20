# Astana IT University: Blockchain Hack 2023 

## Project name

Интерактивная панель мониторинга аналитики криптовалют

## Selected problem

Криптовалюты - это новая и быстро развивающаяся сфера, которая привлекает все больше инвесторов. Однако, эта сфера также характеризуется высокой волатильностью цен и ненадежностью информации

## Team name

TokenTribe

## Participants

* Full name: Халимарден Малика. Email: 222330@astanait.edu.kz
* Full name: Есенаман Дильназ. Email: 222329@astanait.edu.kz
* Full name: Бердбеков Арыстан. Email: 222070@astanait.edu.kz

## Abstract

Наш проект "Интерактивная панель мониторинга криптовалютной аналитики" решает эту проблему, предлагая комплексное решение для мониторинга и анализа криптоданных. Панель включает в себя удобный интерфейс, показывающий информацию о криптовалюте в режиме реального времени. Она также включает в себя такие функции, как графические представления, аутентичные средства проверки и безопасную структуру конгломерата информации. Эти функции позволяют инвесторам принимать более обоснованные решения о своих инвестициях в криптовалюты.

## Demo video

[Link to a demo video showcasing your project, if any. Ensure it is less than 3 minutes long.]

## How to run


### Prerequisites:

Программное обеспечение:
Языки программирования (Python)
Фреймворки (Django)
Системы управления базами данных ( PostgreSQL)

Инструменты:
Ключи API 
Внешние сервисы 

### Running

[Provide specific commands and environment for building and running your project, preferably in a containerized environment.]

Basic example:
```bash
django-admin startproject crypto_dashboard_project
cd crypto_dashboard_project
python manage.py startapp crypto_monitoringһ
```

PYTHON

```apps.py

from django.apps import AppConfig

class CryptoMonitoringConfig(AppConfig):
    default_auto_field = 'django.db.models.BigAutoField'
    name = 'crypto_monitoring'

    def ready(self):
        from . import dash_app  # Импортируем Dash приложение
        dash_app.initialize_plotly_dash(app_name='CryptoMonitoring')

```
```dash_app.py
import dash
import dash_core_components as dcc
import dash_html_components as html
import plotly.express as px
from django_plotly_dash import DjangoDash
from .models import CryptoData  
app = DjangoDash('CryptoMonitoring') 
crypto_data = CryptoData.objects.all()
app.layout = html.Div([
    html.H1('Криптовалютный мониторинг'),
    dcc.Graph(
        figure=px.line(crypto_data, x='timestamp', y='value', title='График изменения цен криптовалют')
    ),
])
```
```ls.py
from django.urls import path, include
urlpatterns = [
    path('crypto/', include('crypto_monitoring.urls')),
]
```

```kms.py
from django.urls import path
from . import views

urlpatterns = [
    path('dashboard/', views.dashboard_view, name='dashboard'),
]
```


## Inspirations

Наша группа была мотивирована растущей потребностью в надежных криптографических данных из-за нестабильности рынка. Мы планировали создать инструмент, который дает точный анализ данных для более эффективного принятия решений в криптопространстве. Так как наша команда столкнулась с ситуацией, когда не могла найти достоверную информацию о криптовалюте, которая была бы необходима для принятия инвестиционных решений

## Technology stack and organization

проект реализован на базе платформы Python с использованием фреймворка Django

## Solutions and features implemented

Наше проект включает в себя удобный интерфейс, показывающий информацию о криптовалюте в режиме реального времени. Он включает в себя такие функции, как графические представления, аутентичные средства проверки и безопасную структуру конгломерата информации. Этап позволяет клиентам с надежным опытом выйти на крипторынки.И хотелось бы добавить информацию о графические представления реализованы с использованием библиотеки Matplotlib, а аутентичные средства проверки реализованы с использованием библиотеки JWT

## Challenges faced

Проблемы на пути развития включали поиск надежной информации в режиме реального времени, обеспечение информационной безопасности и оптимизацию для высоких нагрузок без ущерба для производительности и проблема поиска надежной информации в режиме реального времени решалась с помощью использования нескольких источников информации, а проблема обеспечения информационной безопасности решалась с помощью использования методов шифрования

## Lessons learned

Мы узнали о важности информационного суждения в криптопространстве и о важности создания адаптируемых механизмов для борьбы с колебаниями рекламы.

## Future work

В планы на будущее входит проведение прогнозной аналитики, объединение большего количества источников информации для получения полных знаний и совершенствование мер безопасности для информации клиентов и так же команда TokenTribe планирует добавить в проект функцию прогнозирования цен на криптовалюту, а также функцию интеграции с различными биржами.Эти функции позволят сделать проект еще более полезным для инвесторов

## Additional sources
https://www.sciencedirect.com/science/article/pii/S2667096821000288
