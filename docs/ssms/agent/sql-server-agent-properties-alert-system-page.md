---
title: "Свойства агента SQL Server (страница &quot;Система предупреждений&quot;) | Документация Майкрософт"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.ag.agent.alert.f1
ms.assetid: 3e6d3bfd-20ee-4593-86cc-f65b1c08c69d
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 334a1025cca8100f1ba6bcc0855712a7e5fe0ef0
ms.contentlocale: ru-ru
ms.lasthandoff: 04/11/2017

---
# <a name="sql-server-agent-properties-alert-system-page"></a>Свойства агента SQL Server (страница «Система предупреждений»)
Данная страница используется для просмотра и изменения параметров сообщений, отправляемых предупреждениями агента [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)].  
  
## <a name="options"></a>Параметры  
**Почтовый сеанс**  
Параметры в данном разделе предназначены для настройки почты агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] .  
  
**Включить почтовый профиль**  
Включает почту агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] . По умолчанию почта агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] не включена.  
  
**Почтовая система**  
Устанавливает почтовую систему для использования агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] . Database Mail  
  
> [!NOTE]  
> После изменений системы электронной почты необходимо перезапустить службу агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] , чтобы эти изменения вступили в силу.  
  
**Профиль электронной почты**  
Устанавливает профиль для использования агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] . Для создания нового профиля вы можете также выбрать пункт **\<новый профиль Database Mail...>**.  
  
**Электронные сообщения на пейджер**  
Параметры в этом разделе позволяют настроить электронные сообщения, отправляемые на адреса пейджеров для работы с вашей пейджинговой системой.  
  
**Форматирование адреса для электронных сообщений на пейджер**  
Данный раздел позволяет задать формат адресов и темы, включаемые в электронные сообщения на пейджер.  
  
**Поле «Кому»**  
Задает параметры для строки сообщения **Кому** .  
  
**Префикс**  
Введите любой фиксированный текст, требуемый системой в начале строки **Кому** сообщений, отправляемых на пейджер.  
  
**Пейджер**  
Содержит адрес электронной почты для сообщения между префиксом и суффиксом.  
  
**Суффикс**  
Введите любой фиксированный текст, требуемый пейджинговой системой в конце строки **Кому** сообщений, отправляемых на пейджер.  
  
**Поле «Копия»**  
Задает параметры для строки сообщения **Копия** .  
  
**Префикс**  
Введите любой фиксированный текст, требуемый системой в начале строки **Копия** сообщений, отправляемых на пейджер.  
  
**Пейджер**  
Содержит адрес электронной почты для сообщения между префиксом и суффиксом.  
  
**Суффикс**  
Введите любой фиксированный текст, требуемый пейджинговой системой в конце строки **Копия** сообщений, отправляемых на пейджер.  
  
**Тема**  
Задает параметры для строки темы сообщения.  
  
**Префикс**  
Введите любой фиксированный текст, требуемый системой в начале строки **Тема** сообщений, отправляемых на пейджер.  
  
**Суффикс**  
Введите любой фиксированный текст, требуемый системой в конце строки **Тема** сообщений, отправляемых на пейджер.  
  
**Включить тело электронного письма в сообщение уведомления**  
Включает тело электронного письма в сообщение, отправляемое на пейджер.  
  
**Резервный оператор**  
Данный раздел позволяет задать параметры для резервного оператора.  
  
**Включить резервный оператор**  
Задает резервный оператор.  
  
**Оператор**  
Устанавливает имя оператора для получения уведомлений об отказах.  
  
**Уведомлять с помощью**  
Устанавливает метод для использования при уведомлении резервного оператора.  
  
**Замена токенов**  
Данный раздел позволяет включить токены шагов заданий, которые могут использоваться в заданиях, выполняемых предупреждениями агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] . Дополнительные сведения о токенах шагов заданий см. в разделе [Использование токенов в шагах задания](../../ssms/agent/use-tokens-in-job-steps.md).  
  
> [!IMPORTANT]  
> Все пользователи Windows с разрешением на запись в журнал событий Windows могут получить доступ к шагам заданий, которые активированы предупреждениями агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] . Чтобы избежать этого нарушения безопасности, в [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] токены агента, которые могут использоваться в заданиях, активированных предупреждениями, по умолчанию отключены. К этим токенам относятся: **$(A-DBN)**, **$(A-SVR)**, **$(A-ERR)**, **$(A-SEV)**и **$(A-MSG)**.  
>   
> При необходимости использовать эти токены перед их включением убедитесь, что только члены доверенных групп безопасности Windows, таких как группа «Администраторы», обладают разрешением на работу с журналом событий компьютера, на котором находится [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] .  
  
**Заменить токенами всех ответов заданий на предупреждения**  
Установите этот флажок, чтобы включить замену токенов для заданий, активизированных предупреждениями [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] .  
  
## <a name="see-also"></a>См. также:  
[Операторы](../../ssms/agent/operators.md)  
[Настройка почты агента SQL Server на использование компонента Database Mail](http://msdn.microsoft.com/en-us/4b8b61bd-4bd1-43cd-b6e5-c6ed2e101dce)  
[Database Mail](http://msdn.microsoft.com/en-us/9e4563dd-4799-4b32-a78a-048ea44a44c1)  
  
