---
title: Введение в мониторинг служб Analysis Services с SQL Server Profiler | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, Analysis Services
- monitoring Analysis Services [SQL Server]
- performance [Analysis Services]
- performance [Analysis Services], SQL Server Profiler
- Profiler [SQL Server Profiler], Analysis Services
ms.assetid: 568ec549-5ddc-493a-b9f8-3bdc548b562e
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: e81e0e7acf0d31be45f1d653ed2a6926f55b57fe
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48113414"
---
# <a name="introduction-to-monitoring-analysis-services-with-sql-server-profiler"></a>Введение в мониторинг служб Analysis Services при помощи приложения SQL Server Profiler
  Приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] можно использовать для мониторинга событий, формируемых экземпляром служб [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. С помощью приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]можно выполнять следующее:  
  
-   Проводить мониторинг производительности экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
-   Выполнять отладку инструкций многомерных выражений.  
  
-   Выявлять инструкции многомерных выражений, выполняющиеся слишком медленно.  
  
-   Проверять инструкции многомерных выражений на стадии разработки проекта в пошаговом режиме, чтобы убедиться, что код выполняется так, как ожидается.  
  
-   Устранять проблемы в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] с помощью перехвата событий на рабочей системе и воспроизведения их на отладочной. Этот подход полезно использовать при тестировании или отладке. Он позволяет пользователям использовать рабочую систему без помех.  
  
-   Выполнять аудит и отслеживание действий, происходящих в экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Администратор по безопасности может просмотреть любое из событий аудита. Это включает успешную или неуспешную попытку входа, разрешения на доступ к инструкциям и объектам.  
  
-   Отображение на экране данных о зарегистрированных событиях или сбор и сохранение данных о каждом событии в файл или таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для дальнейшего анализа или воспроизведения. При воспроизведении данных можно повторно запустить сохраненные события в порядке их возникновения в реальном времени или пошаговом режиме.  
  
## <a name="using-sql-server-profiler"></a>Использование приложения SQL Server Profiler  
 Чтобы использовать приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] для создания или воспроизведения трассировок, необходимо быть членом роли сервера служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] . Член роли сервера служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] может запускать приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] из группы программ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в меню **Пуск** .  
  
 При использовании приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]обратите внимание на следующее:  
  
-   Определения трассировок хранятся в базе данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] с использованием инструкции CREATE.  
  
-   Несколько трассировок можно запустить одновременно.  
  
-   Несколько соединений могут получать события из одной трассировки.  
  
-   Трассировка может продолжаться при остановке и перезапуске служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .  
  
    > [!NOTE]  
    >  Пароли в событиях трассировки скрыты и представлены в виде ******.  
  
 Чтобы обеспечить оптимальную производительность, используйте приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] для мониторинга только наиболее важных событий. Мониторинг слишком многих событий приводит к перегрузке и может привести к избыточному увеличению размера файла или таблицы трассировки, особенно при длительном мониторинге. Кроме того, для ограничения количества собираемых данных и предотвращения увеличения трассировок используйте фильтры.  
  
## <a name="see-also"></a>См. также  
 [События трассировки служб Analysis Services](../trace-events/analysis-services-trace-events.md)   
 [Создание трассировок Profiler для воспроизведения &#40;служб Analysis Services&#41;](create-profiler-traces-for-replay-analysis-services.md)  
  
  
