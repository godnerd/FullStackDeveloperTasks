## Задание №1. БД прайс-листов.

### Средства

Платформа: Microsoft .NET Framework 4.0

Технология: ASP.NET MVC

Язык программирования: C#

База данных: Microsoft SQL Server Express

### Задача

Цель: разработать систему, предназначенную для ведения базы данных прайс-листов на продукцию.

### Требования к архитектуре:

1. Работа с системой должна осуществляться через WEB-интерфейс;
2. Хранение данных должно осуществляться в СУБД MS SQL Server Express;

### Функциональные требования:

Информация о товаре должна включать следующие данные:
1. Код;
2. Категория;
3. Наименование;
4. Цена;
5. Количество на складе;
6. Примечание.

Пример списка категорий товара:
1. Процессоры;
2. Материнские платы;
3. Оперативная память;
4. Видеокарты;
5. Жесткие диски;
6. Корпуса;
7. Периферия;
8. Разное.

Процесс работы пользователей с системой должен включать в себя следующие функции:
1. Просмотр прайс-листа;
2. Ввод информации о новом товаре;
3. Редактирование информации о товаре;
4. Удаление информации о товаре;
5. Фильтр по категории и цене;
6. Сортировка по цене и количеству на складе;
7. Редактирование справочника категорий.

## Задание №2. Парсер.

### Средства

Платформа: Microsoft .NET Framework 2.0 и выше

Язык программирования: C#

### Задача

Цель: разработать консольное приложение, предназначенное для обработки исходного файла в определенном формате.

### Требования к архитектуре:

1. Программа должна предоставлять собой консольное приложение;
2. Программа должна корректно обрабатывать возможные ошибки;

### Входные параметры:

1. Имя входного файла;
2. Имя выходного файла.

#### Пример входных параметров:

Task2App.exe “input.txt” “output.xml”

#### Пример входного файла:

     Begin Application
         Name="Приложение"
         Begin Files
             Begin File
                 Name="app.exe"
             End File
         End Files
     End Application

     Begin Package
         Name="Microsoft Visual Studio 2005 Report Viewer"
         LicenseAgreement="EULA0"
         PackageCode="Microsoft.ReportViewer.8.0.en"

         Begin Commands
             Reboot="Defer"
             Begin Command
                 PackageFile="ReportViewer\ReportViewer.exe"
                 Arguments=" /q:a /q /l""
                 EstimatedInstalledBytes="5000000"
                 EstimatedInstallSeconds="300"

                 Begin InstallConditions
                     Begin BypassIf
                         Property="ReportViewerInstalled"
                         Compare="ValueNotEqualTo"
                         Value="0"
                     End BypassIf

                     Begin FailIf
                         Property="AdminUser"
                         Compare="ValueEqualTo"
                         Value="false"
                         Text="Administrator permissions are required to install Microsoft Visual Studio 2005 Report Viewer. Contact your administrator."
                     End FailIf
                End InstallConditions

                Begin ExitCodes
                    Begin ExitCode
                        Value="0"
                        Result="Success"
                    End ExitCode

                    Begin ExitCode
                        Value="3010"
                        Result="SuccessReboot"
                    End ExitCode

                    Begin ExitCode
                        Value="4097"
                        Result="Fail"
                        Text="Administrator permissions are required to install Microsoft Visual Studio 2005 Report Viewer. Contact your administrator."
                    End ExitCode

                    Begin DefaultExitCode
                        Result="Fail"
                        FormatMessageFromSystem="true"
                        Text="A failure occurred attempting to install Microsoft Visual Studio 2005 Report Viewer."
                    End DefaultExitCode
                End ExitCodes
            End Command
        End Commands

        Begin InstallChecks
            Begin ExternalCheck
                Property="ReportViewerInstalled"
                PackageFile="ReportViewer\ReportViewerChk.exe"
            End ExternalCheck
        End InstallChecks

        Begin PackageFiles
            CopyAllPackageFiles="false"

            Begin PackageFile
                Name="ReportViewer\ReportViewer.exe"
                HomeSite="http://go.microsoft.com/fwlink/?LinkId=49981"
                PublicKey="3082010A0282010100"
                Size="1921224"
            End PackageFile

            Begin PackageFile
                Name="ReportViewer\ReportViewerChk.exe"
                PublicKey="3082010A0282010101"
            End PackageFile
        End PackageFiles

        Begin RelatedProducts
            Begin DependsOnProduct
                Code="Microsoft.Net.Framework.2.0"
            End DependsOnProduct
        End RelatedProducts
    End Package

    Begin Package
        Name="Prerequisutes Studio 2.0"
        LicenseAgreement="EULA1"
        PackageCode="PrerequisitesStudio.2.0"

        Begin Commands
            Reboot="Immediate"

            Begin Command
                PackageFile="PrerequisitesStudio\pStudio2.exe"
                Arguments=" /i /q"
                EstimatedInstallSeconds="1000000"
                EstimatedInstalledBytes="400"
                EstimatedTempBytes="0"
            End Command
        End Commands

        Begin PackageFiles
            CopyAllPackageFiles="true"

            Begin PackageFile
                Name="PrerequisitesStudio\pStudio2.exe"
                Hash="DG874DF54VTN8S5B8JS6"
            End PackageFile
        End PackageFiles
    End Package

#### Формат выходного файла:
<Packages>
    <Package Name=“Microsoft Visual Studio 2005 Report Viewer” Code=“Microsoft.ReportViewer.8.0.en” />

<Package Name=“Prerequisutes Studio 2.0” Code=“PrerequisitesStudio.2.0” />

</Packages>

<Files>

<File Name=“ReportViewer\ReportViewer.exe” Hash=“3082010A0282010100” Arguments=“ /q:a /q /l” />

<File Name=“ReportViewer\ReportViewerChk.exe” Hash=“3082010A0282010101” Arguments=“” />

<File Name=“PrerequisitesStudio\pStudio2.exe” Hash=“DG874DF54VTN8S5B8JS6” Arguments=“ /i /q” />

</Files>
