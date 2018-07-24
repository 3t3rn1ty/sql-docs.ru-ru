---
title: Создание междоменного правила | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- data-quality-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dm.testcdrule.f1
- sql12.dqs.dm.cdrules.f1
ms.assetid: 0f3f5ba4-cc47-4d66-866e-371a042d1f21
caps.latest.revision: 12
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 198f3c46c97039fb788cb924a5980f0b6cd75145
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37295444"
---
# <a name="create-a-cross-domain-rule"></a>Создание междоменного правила
  В этом разделе описано, как создать междоменное правило для составного домена в базе знаний служб [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS). Междоменное правило проверяет связь между значениями в отдельных доменах, включенных в составной домен. Междоменное правило должно выполняться в составном домене, чтобы значения в домене были точными и соответствовали требованиям бизнеса. Междоменное правило используется для проверки, исправления и стандартизации значений в домене.  
  
 Каждое предложение If и Then в междоменном правиле определяется для одного из доменов составного домена. Каждое предложение должно быть определено для своего домена. Междоменное правило должно связывать несколько отдельных доменов; в составном домене нельзя определить простое доменное правило (только для одного домена). Это следует делать путем определения доменного правила для отдельного домена. Предложения If и Then могут содержать одно или несколько условий.  
  
 Междоменное правило, содержащее определительные условия, будет применять логику правила к синонимам значений в условиях, в также к самим значениям. Определительными условиями для предложений If и Then являются Значение равно, Значение не равно, Значение в наборе или Значение не в наборе. Например, предположим, что имеется следующее междоменное правило для составного домена: если для «City» значение равно «Los Angeles», то для «State» значение равно «CA». «Если "Los Angeles" и "LA" являются синонимами, это правило воспримет правильно "Los Angeles CA" и "LA CA", но возвратит ошибку для "Los Angeles WA" и "LA WA".  
  
 Помимо информирования о выполнении междоменного правила определительное предложение *Then* в междоменном правиле, **Значение равно**, также исправляет данные во время проведения очистки данных. Дополнительные сведения см. в разделе [коррекция данных с использованием Определительных междоменных правил](../../2014/data-quality-services/cleanse-data-in-a-composite-domain.md#CDCorrection) в [Очистка данных в составном домене](../../2014/data-quality-services/cleanse-data-in-a-composite-domain.md).  
  
 Междоменные правила рассматриваются после всех простых правил, затрагивающих только один домен. Только если для значения выполняются простые правила (если они существуют), к нему применяется междоменное правило. Составной домен и отдельные домены, для которых выполняется правило, должны быть определены, прежде чем правило будет применяться.  
  
##  <a name="BeforeYouBegin"></a> Перед началом  
  
###  <a name="Prerequisites"></a> Предварительные требования  
 Чтобы создать междоменное правило, необходимо предварительно создать и открыть составной домен.  
  
###  <a name="Security"></a> безопасность  
  
####  <a name="Permissions"></a> Permissions  
 Для создания междоменного правила необходимо иметь в базе данных DQS_MAIN роль dqs_administrator или dqs_kb_editor.  
  
##  <a name="Create"></a> Создание междоменных правил  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)] [Запуск клиентского приложения Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).  
  
2.  На главном экране клиента [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] откройте или создайте базу знаний. Выберите операцию **Управление доменами** , а затем нажмите кнопку **Открыть** или **Создать**. Дополнительные сведения см. в разделе [Создание базы знаний](../../2014/data-quality-services/create-a-knowledge-base.md) или [Открытие базы знаний](../../2014/data-quality-services/open-a-knowledge-base.md).  
  
    > [!NOTE]  
    >  Управление доменами осуществляется на странице клиента службы Data Quality Services, которая содержит пять вкладок для отдельных операций управления доменом. Это не процесс, управляемый мастером; любая операция управления может быть выполнена отдельно.  
  
3.  Из **Списка доменов** на странице **Управление доменами** выберите составной домен, для которого надо создать доменное правило, или просто создайте новый составной домен. Если вам нужно создать новый домен, см. в разделе [создать составной домен](../../2014/data-quality-services/create-a-composite-domain.md).  
  
4.  Щелкните вкладку **Правила CD** .  
  
5.  Нажмите кнопку **Добавить новое доменное правило**и введите имя и описание для правила.  
  
6.  Установите флажок **Активное** , чтобы указать, что правило должно применяться (по умолчанию), и снимите этот флажок, чтобы правило не применялось.  
  
7.  Создайте предложение If следующим образом.  
  
    1.  На панели предложения If в списке доменов выберите один из отдельных доменов, включенных в составной домен, который будет субъектом в предложении If. Вы можете выбрать любой отдельный домен в составном домене.  
  
    2.  Выберите условие из раскрывающегося списка в качестве первого условия предложения.  
  
    3.  Если условию требуется значение, введите значение в текстовом поле, связанном с условием.  
  
    4.  Если предложению требуется другое условие, щелкните **Добавить новое условие в выбранное предложение**. Выберите оператор, выберите условие и введите значение для условия, если оно требуется.  
  
    5.  Чтобы изменить порядок условий, выберите условие, щелкнув слева от него, и нажмите кнопку со стрелками вверх или вниз.  
  
    6.  Чтобы скрыть условия, нажмите знак «минус» слева от имени домена. Нажмите знак «плюс» для отображения условий.  
  
8.  Создайте предложение Then, выбрав отдельный домен, отличный от субъекта предложения If, в списке доменов на панели предложения Then. Затем постройте предложение Then, используя те же шаги, что и при построении предложения If.  
  
9. Перейти к процедуре проверки ниже.  
  
##  <a name="Test"></a> Проверка междоменных правил  
  
1.  Проверьте междоменное правило следующим образом.  
  
    1.  Нажмите значок **Применить выбранное доменное правило к тестовым данным** в правом верхнем углу панели составного домена.  
  
    2.  В диалоговом окне **Проверка доменного правила** щелкните значок **Добавить новый тестовый терм для доменного правила** .  
  
    3.  Введите тестовые значения для домена, связанного с предложением If, и для домена, связанного с предложением Then. Тестовые значения, введенные в предложение If, должны отвечать условиям этого предложения, иначе появится знак вопроса в столбце **Validity** , указывающий, что междоменное правило неприменимо к тестовым данным.  
  
    4.  Нажмите снова значок **Добавить новый тестовый терм для доменного правила** , чтобы добавить другой набор тестовых значений.  
  
    5.  Нажмите значок **Проверить доменное правило на всех термах** . Если набор тестовых значений допустим, службы DQS установят флажок в столбце **Validity** для этой строки. Если же набор тестовых значений недопустим, службы DQS установят треугольник с восклицательным знаком в столбце Validity для этой строки.  
  
    6.  После завершения проверки нажмите **Закрыть** в диалоговом окне **Проверка правила для составного домена** .  
  
2.  После завершения вашего междоменные правила щелкните **Готово** для выполнения действия по управлению доменами, как описано в разделе [завершение операции управления доменами](../../2014/data-quality-services/end-the-domain-management-activity.md).  
  
##  <a name="FollowUp"></a> Дальнейшие действия. После создания междоменного правила  
 Создав перекрестное правило, можно выполнить для этого домена другие задачи управления доменами, провести обнаружение знаний для добавления знаний в домен или добавить в домен политику сопоставления. Дополнительные сведения см. в разделах [Обнаружение набора знаний](../../2014/data-quality-services/perform-knowledge-discovery.md), [Управление доменом](../../2014/data-quality-services/managing-a-domain.md) и [Создание политики сопоставления](../../2014/data-quality-services/create-a-matching-policy.md).  
  
  