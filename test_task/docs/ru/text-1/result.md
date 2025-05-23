# Как подключиться к серверу по SSH?

> SSH (Secure Shell) — протокол для безопасного доступа к удалённому серверу. 


Выберите вашу операционную систему:

{% list tabs %}

- Windows

    Рассмотрим вариант подключения через **PuTTY**. Эта бесплатная программа для Windows состоит из одного запускаемого файла и не требует установки.


    Чтобы подключиться к серверу через PuTTY:

    ## Ути-пути

    1. Скачайте нужную вам версию `putty.exe` по [ссылке](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html), немного ниже заголовка _Alternative binary files._. 
    
    {% note tip "32 или 64" %}

    Выбор версии приложения зависит от разрядности Windows: 32-bit или 64-bit. Если вы не знаете разрядность вашей системы, прочтите [официальную документацию](https://support.microsoft.com/ru-ru/office/%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0%D0%BB%D0%B8%D1%87%D0%B8%D1%8F-32-%D0%B8%D0%BB%D0%B8-64-%D1%80%D0%B0%D0%B7%D1%80%D1%8F%D0%B4%D0%BD%D0%BE%D0%B9-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%86%D0%B8%D0%BE%D0%BD%D0%BD%D0%BE%D0%B9-%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D1%8B-windows-%D0%BD%D0%B0-%D0%BA%D0%BE%D0%BC%D0%BF%D1%8C%D1%8E%D1%82%D0%B5%D1%80%D0%B5-aac162a1-0cb3-46f2-888f-2f22897396ce#:~:text=%D0%9D%D0%B0%D0%B6%D0%BC%D0%B8%D1%82%D0%B5%20%D0%BA%D0%BD%D0%BE%D0%BF%D0%BA%D1%83%20%D0%9F%D1%83%D1%81%D0%BA%2C%20%D0%B2%D0%B2%D0%B5%D0%B4%D0%B8%D1%82%D0%B5%20%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%B0,%D1%83%D0%BA%D0%B0%D0%B7%D0%B0%D0%BD%D0%BE%2064%2D%D1%80%D0%B0%D0%B7%D1%80%D1%8F%D0%B4%D0%BD%D0%B0%D1%8F%20%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%86%D0%B8%D0%BE%D0%BD%D0%BD%D0%B0%D1%8F%20%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%B0.) от Microsoft. 

    {% endnote %}

    2. Откройте скачанный файл `putty.exe`.

    ### ПуТТИшествие на сервер




    3. В открывшемся окне заполните следующие данные:


        * В поле `Host Name (or IP adress)` введите IP-адрес или доменное имя вашего сервера.
        *  В поле `Port` будет число `22`. Порт 22 используется по умолчанию протоколом SSH.
        *  В поле `Connection type` выберите опцию `SSH`.  
        *  В поле `Close windows on exit` выберите опцию `Only on clean exit`.
        *  Чтобы сохранить эту конфигурацию на будущее, в поле `Saved Sessions` введите её имя и нажмите кнопку **Save**.
        *  Нажмите кнопку **Open**.

    <figure style="display: grid; place-items: center;" class = "photo_content">
      <img src="/images/putty_.png" alt="Окно программы PuTTY"/>
      <figcaption>Окно программы PuTTY  
      </figcaption>
    </figure>            

  При первом подключении к серверу появится предупреждение системы безопасности.
  
  Нажмите кнопку **Да**, чтобы продолжить соединение.

    <figure style="display: grid; place-items: center;" class = "photo_content">
      <img src="/images/alert.png" alt="Предупреждение системы безопасности"/>
      <figcaption>Жмём да
      </figcaption>
    </figure>      

  6. В появившейся командной строке введите login пользователя сервера. Например, `admin`. Нажмите **Enter**.

  ```bash
  login: admin
  ```

  7. Затем введите пароль пользователя. Никаких символов не будет видно: так задумано, чтобы никто не подсмотрел.

  ```bash
  login: admin
  admin@192.0.2.1's password:
  ```
  8. Ввели? Нажмите **Enter.**

  {% note warning "Смените пароль!" %}

  Он выдаётся при первоначальной настройке сервера. Смените пароль сразу: стандартные пароли часто уязвимы.  


  {% endnote %}



  

  После успешного подключения откроется командная строка для управления сервером.

  Чтобы посмотреть доступные команды, введите `?` и нажмите **Enter**.


  ```bash
  login: admin
  admin@192.0.2.1's password:
  Enter '?' to view avaliable commands.
  _bmc>
  ```

- Linux/MacOS

  Ваша система уже готова к работе — подключайтесь к серверу через SSH **напрямую из терминала**.

  ## Пошагово:
  1. Откройте терминал сочетанием клавиш `Ctrl + Alt + T` или найдите «Терминал» в поиске.

  2. В открытом терминале выполните команду:

  ```bash
  ssh admin@192.0.2.1
  ```
  где:
  * ssh — протокол SSH
  * admin — ваш логин для входа 
  * 192.0.2.1 — IP-адрес вашего сервера

  3. Затем введите пароль. Никаких символов не будет видно: так задумано, чтобы никто не подсмотрел. Нажмите **Enter**.

  {% note tip "Смените пароль!" %}

  И запомните его: вводить придётся каждый раз при входе.
 

  {% endnote %}

  При первом подключении к серверу появится предупреждение системы безопасности. Нажмите кнопку **Да**, чтобы продолжить соединение.

  После успешного подключения откроется командная строка для управления сервером.

{% endlist %}
