---
title: "Compatibilidad de conmutación por error de la base de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09347fdd-2929-4ed9-b0d8-698508663ecd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bbc795191eb2c13ca35d55846719cebc20d61a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="database-failover-support"></a>Compatibilidad con la conmutación por error de la base de datos
Puede pasar una instancia de la **PolicyFetchErrorHandler** delegado como un parámetro a los constructores sobrecargados de la **directiva** clase. Cuando se produce un error al capturar los detalles de la directiva de la base de datos, se invoca la instancia del delegado. También puede usar un bloque try-catch para capturar **capturar** y **RuleStoreCompatibilityException** las excepciones que se producen cuando el motor de reglas no se puede conectar al motor de reglas base de datos.  
  
 Si no se pasa una instancia de la **PolicyFetchErrorHandler** delegado como un parámetro a la **directiva** constructor, o si utiliza la **CallRules** forma en un orquestación, a continuación, si un error se produce al capturar los detalles de la directiva de la base de datos, producirán los eventos siguientes:  
  
1.  El motor de reglas utiliza los valores de la **PolicyFetchErrorHandlerAssembly** y **PolicyFetchErrorHandlerClass** entradas del registro bajo **HKEY_LOCAL_MACHINE\Software\Microsoft\ BusinessRules\3.0**. Los valores predeterminados de la **PolicyFetchErrorHandlerAssembly** y **PolicyFetchErrorHandlerClass** entradas del registro son **Microsoft.BizTalk.RuleEngineExtensions**y **Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper** respectivamente.  
  
2.  El **ExceptionHelper** la clase implementa la **IPolicyFetchErrorMaker** interfaz.  
  
3.  El motor de reglas, se invoca el **get_ErrorHandler** método en el **IPolicyFetchErrorMaker** de la interfaz para obtener un puntero al método de control de errores y lo invoca.  
  
4.  El método de control de errores predeterminado, se invoca el **SetDBFailure** método, que se define en el archivo BTSDBAccessor.dll.  
  
5.  El **SetDBFailure** método hace que el servicio de BizTalk cerrar. El servicio de BizTalk se reinicia transcurrido un minuto y se cierra si las bases de datos siguen sin estar disponibles. Este ciclo se repite hasta que las bases de datos están disponibles.