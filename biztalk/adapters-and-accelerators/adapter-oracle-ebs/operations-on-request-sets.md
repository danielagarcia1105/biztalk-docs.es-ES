---
title: Operaciones con conjuntos de solicitud | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0537354d-821e-4cf9-a4d1-f4e7d1643df9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8051a94df28df4090f78287070c5143e6f866ed7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-request-sets"></a>Operaciones con conjuntos de solicitud
Una solicitud establecida en Oracle E-Business Suite es un conjunto de informes y programas simultáneos que se organizan en varias fases. Puede usar una única solicitud configurada para ejecutarse un conjunto de informes y programas simultáneos. Solicitar conjuntos se dividen en una o varias fases y cada fase contiene un conjunto de informes y programas simultáneos. Estas fases están vinculadas entre sí, y se define el orden de la ejecución de cada fase. Para más información específica de Oracle acerca de los conjuntos de solicitud, vaya a [http://go.microsoft.com/fwlink/p/?LinkId=129539](http://go.microsoft.com/fwlink/p/?LinkId=129539).  
  
 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]permite ejecutar conjuntos de solicitudes en Oracle E-Business Suite. Los conjuntos de solicitud se exponen como operaciones en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Dado que un conjunto de solicitud contiene un conjunto de programas simultáneos, esos programas simultáneos son los parámetros de entrada para una solicitud de operación del conjunto. Además de los programas simultáneos, la operación de establecimiento de solicitud toma cuatro parámetros de tipo complejo y un parámetro de tipo simple como entrada.  
  
> [!IMPORTANT]
>  Debe establecer el contexto de las aplicaciones para la solicitud se establece [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para poder realizar cualquier operación en conjuntos de solicitudes. Esto es porque el contexto de las aplicaciones de configuración facilita transacciones seguras en Oracle E-Business Suite estableciendo las preferencias del usuario (como la configuración de responsabilidad, su organización y language) y control de acceso de un artefacto. Para obtener información sobre el contexto de las aplicaciones y cómo configurarlo, vea [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
## <a name="complex-type-parameters"></a>Parámetros de tipo complejo
  
-   **SetRelClassOptions**: le permite establecer opciones de programación para el conjunto de solicitud. Si se establecen SetRelClassOptions y SetRepeatOptions SetRelClassOptions tendrá prioridad. SetRelClassOptions toma las siguientes opciones como parámetros:  
  
    -   **Aplicación**: indica el nombre corto de la aplicación asociada con el conjunto de solicitud.  
  
    -   **ClassName**: indica el nombre de la clase asociada con el conjunto de solicitud.  
  
    -   **CanceOrHold**: indica la marca de suspensión o Cancel.  
  
    -   **StaleDate**: indica la fecha en o después de que este conjunto de solicitud se cancelará si el conjunto de solicitud no se ha ejecutado todavía.  
  
    -   **ContinueOnFail**: indica si el envío de conjunto de solicitud debe continuar o iniciar una excepción en caso de que se produce un error en SetRelClassOptions. Puede especificar "True" (continuar) o "False" (producirán una excepción).  
  
-   **SetPrintOptions**: le permite establecer las opciones de impresión para el conjunto de solicitud. SetPrintOptions toma las siguientes opciones como parámetros:  
  
    -   **Impresora**: indica el nombre de impresora que debe enviarse la solicitud establecer salida.  
  
    -   **Estilo**: indica el estilo de impresión que se usa para imprimir la solicitud establecer salida. Por ejemplo, puede especificar la orientación ("Horizontal" o "Vertical").  
  
    -   **Copias**: indica el número de copias que desea imprimir de la solicitud establecer salida.  
  
    -   **SaveOutput**: indica si se debe o no guardar el archivo de salida. Puede especificar "True" o "False".  
  
    -   **PrintTogether**: solo es aplicable a las solicitudes de subcarpetas. Indica cómo se imprime el resultado de las solicitudes de subcarpetas. Si especifica "Y", se imprime el resultado de las solicitudes secundarias solo después de que todas las solicitudes secundarias están completos. Si especifica "N", la salida de cada solicitud secundaria se imprime tal y como se complete.  
  
    -   **ContinueOnFail**: indica si el envío de conjunto de solicitud debe continuar o iniciar una excepción en caso de que se produce un error en SetPrintOptions. Puede especificar "True" (continuar) o "False" (producirán una excepción).  
  
-   **SetRepeatOptions**: le permite establecer las opciones de repetición para el conjunto de solicitud. SetRepeatOptions toma las siguientes opciones como parámetros:  
  
    -   **RepeatTime**: indica la hora del día para repetir el conjunto de solicitud.  
  
    -   **RepeatInterval**: este parámetro solo es aplicable cuando **RepeatTime** es NULL. Indica el intervalo entre los reenvíos de la solicitud. Use esta opción junto con **RepeatUnit** para especificar el tiempo entre los reenvíos.  
  
    -   **RepeatUnit**: este parámetro solo es aplicable cuando **RepeatTime** es NULL. La unidad de tiempo que se utiliza junto con **RepeatInterval** para especificar el tiempo entre los reenvíos de la solicitud. Puede especificar "Minutes", "Hours", "Days" o "Meses".  
  
    -   **RepeatType**: este parámetro solo es aplicable cuando **RepeatTime** es NULL. Indica si el intervalo de repetición se aplica después de ejecución del conjunto de "inicio" de una solicitud anterior o ejecución del conjunto de "final" de una solicitud anterior.  
  
    -   **RepeatEndTime**: indica la fecha y hora para detener volver a enviar el conjunto de solicitud.  
  
    -   **ContinueOnFail**: indica si el envío de conjunto de solicitud debe continuar o iniciar una excepción en caso de que se produce un error en SetRepeatOptions. Puede especificar "True" (continuar) o "False" (producirán una excepción).  
  
-   **SetNlsOptions**: le permite establecer las opciones de NLS para el conjunto de solicitud. SetNlsOptions toma las siguientes opciones como parámetros:  
  
    -   **Idioma**: indica el idioma NLS.  
  
    -   **Idioma**: indica el territorio del lenguaje.  
  
    -   **ContinueOnFail**: indica si el envío de conjunto de solicitud debe continuar o iniciar una excepción en caso de que se produce un error en SetNlsOptions. Puede especificar "True" (continuar) o "False" (producirán una excepción).  
  
## <a name="simple-type-parameter"></a>Parámetro de tipo simple
  
 **StartTime**: indica el tiempo en el que el conjunto de solicitud debe iniciar su ejecución.  
  
 Si la solicitud completa correctamente, una solicitud simultánea que se devuelve el identificador. En caso contrario, se devuelve "0".  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)