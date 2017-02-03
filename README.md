# causaria-themes

# Установка темы lagunita: #

## Шаг 1 - останавливаем memcached: ##
>     telnet localhost 11211
>     flush_all
>     quit

## Шаг 2 - клонируем тему в /edx/edxapp/themes  ##

>     cd /edx/edxapp/themes 
> 
>     clone https://github.com/causariaLMS/causaria-themes.git

Шаг 3 - прописываем в *lms.env.json* 

 >     "COMPREHENSIVE_THEME_DIRS": [
>         "/edx/edxapp/themes"
> 
>     "USE_CUSTOM_THEME":  true
>  
>     "THEME_NAME": "lagunita", 
>  
>     "DEFAULT_SITE_THEME": "lagunita", 

Шаг 3 - Устраняем ошибки прав доступа


> удаляем всё из папки */var/tmp/mako_lms/*
> 
>  удаляем *staticfiles* из папки */edx/var/edxapp*
>  
>  ставим права для edxapp на lagunita
 

Шаг 4 - компилим тему

>     sudo -H -u edxapp bash
>     source /edx/app/edxapp/edxapp_env
>     cd /edx/app/edxapp/edx-platform
>     paver update_assets lms --settings=aws --themes=lagunita

Должно получиться как здесь {{http://edx.fpkmgppu.ru}}
