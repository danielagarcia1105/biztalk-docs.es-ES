---
title: "Operaciones en programas simultáneos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbc40e4c-d5a1-4763-9683-09a744e5b656
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bd7aae5d90c85e913c0e65a20f1d03e81c526e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-concurrent-programs"></a>Operaciones en programas simultáneos
Programas simultáneos en Oracle E-Business Suite aparecen como operaciones en [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].  Además de los programas simultáneos específicos a una aplicación de Oracle, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] también expone las tres operaciones estándares siguientes: Get_Status, Wait_For_Request y Submit_Request. Esto implica que si una aplicación de Oracle tiene dos programas simultáneos, se expondrán cinco operaciones: uno para cada programa simultáneo y tres para las operaciones estándares.  
  
 Para obtener información acerca de:  
  
-   Examinar y buscar programas simultáneos, consulte [exploración, búsqueda y obtener metadatos para las operaciones de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  
  
-   Cómo invocar programas simultáneos en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [invocar programas simultáneos en Oracle E-Business Suite mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md).  
  
> [!IMPORTANT]
>  Debe establecer el contexto de las aplicaciones para programas simultáneos en [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para poder realizar cualquier operación en programas simultáneos. Esto es porque el contexto de las aplicaciones de configuración facilita transacciones seguras en Oracle E-Business Suite estableciendo las preferencias del usuario (como la configuración de responsabilidad, su organización y language) y control de acceso de un artefacto. Para obtener información sobre el contexto de las aplicaciones y cómo configurarlo, consulte Establecer contexto de la aplicación[establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
 Las secciones siguientes proporcionan información acerca de las operaciones expuestas por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para programas simultáneos.  
  
##  <a name="Concurrent"></a>Operación de < Concurrent_Program_Name >  
 Como se mencionó anteriormente, habrá tantas operaciones < Concurrent_Program_Name > como el número de programas simultáneos en una aplicación de Oracle. La operación < Concurrent_Program_Name > tiene cinco parámetros estándares: tres de tipo complejo y dos de tipo simple.  
  
> [!NOTE]
>  Para los programas simultáneos que no exponen sus metadatos, el adaptador de Oracle E-Business expone 100 parámetros opcionales para cada uno de estos programas simultáneos. Para invocar correctamente estos programas simultáneos, el usuario debe consultar la documentación de Oracle E-Business Suite para averiguar los parámetros de un programa simultáneo que requieren un valor y especifíquelos. Un ejemplo de este tipo de programa simultánea es **importación de Journal** (nombre real: **GLLEZL**) en el **contabilidad** aplicación.  
  
 **Parámetros de tipo complejo**  
  
-   **SetOptions**: le permite establecer opciones para el programa simultáneo antes de enviar la solicitud. SetOptions toma las siguientes opciones como parámetros:  
  
    -   **Implícita**: indica si se muestran las solicitudes simultáneas en el formulario del usuario solicitudes simultáneas en Oracle E-Business Suite. Puede especificar cualquiera de los siguientes cuatro valores: **No**, **Sí**, **Error** o **advertencia**. Especificar **n**hace que las solicitudes que se mostrará en el formulario del usuario solicitudes simultáneas en Oracle E-Business Suite. Especificar **Sí** implica que la solicitud se puede ver sólo en forma de solicitudes simultáneas con privilegios del administrador del sistema. Especificar **Error** hace que la solicitud que se mostrará en forma de solicitudes simultáneas del usuario solo si se produce un error. Especificar **advertencia** hace que la solicitud para que se muestre en if solo del formulario de solicitudes simultáneas del usuario no existe una advertencia o un error.  
  
    -   **Protegido**: indica si la solicitud simultánea está protegida frente a las actualizaciones realizadas con el formato de solicitudes simultáneas en Oracle E-Business Suite. Puede especificar **Sí** (protegido) o **No** (no protegido).  
  
    -   **Idioma**: indica el idioma de la compatibilidad de idioma nacional (NLS). Si no se especifica ningún valor, el valor predeterminado es el idioma actual.  
  
    -   **Territorio**: indica el territorio del lenguaje. Si no se especifica ningún valor, el valor predeterminado es el territorio de lenguaje actual.  
  
    -   **ContinueOnFail**: indica si el envío de solicitudes simultáneas debe continuar o iniciar una excepción en caso de **SetOptions** se produce un error. Puede especificar **True** (continuar) o **False** (producir una excepción).  
  
-   **SetPrintOptions**: le permite establecer las opciones de impresión para el programa simultáneo antes de enviar la solicitud. SetPrintOptions toma las siguientes opciones como parámetros:  
  
    -   **Impresora**: indica el nombre de impresora que se debe enviar la salida de solicitudes simultáneas. No se puede invalidar esta opción de impresión si ya se ha establecido en el formulario de programas simultáneos en Oracle E-Business Suite.  
  
    -   **Estilo**: indica el estilo de impresión que se usa para imprimir la salida de solicitudes simultáneas. Por ejemplo, puede especificar la orientación (**horizontal** o **vertical**). Si ya se ha establecido el estilo de impresión en el formulario de programas simultáneos en Oracle E-Business Suite y el **estilo necesario** casilla de verificación está activada, no se puede invalidar esta opción de impresión.  
  
    -   **Copias**: indica el número de copias que desea imprimir de la salida de solicitudes simultáneas.  
  
    -   **SaveOutput**: indica si se debe o no guardar el archivo de salida. Puede especificar **Sí** o **No**.  
  
    -   **PrintTogether**: solo es aplicable a las solicitudes que contienen las solicitudes de subcarpetas. Indica cómo se imprime el resultado de las solicitudes de subcarpetas. Si especifica **Y**, los resultados de las solicitudes secundarias se imprimen solo después de que todas las solicitudes secundarias están completos. Si especifica **N**, se imprime el resultado de cada solicitud secundaria cuando éste completa.  
  
    -   **ContinueOnFail**: indica si el envío de solicitudes simultáneas debe continuar o iniciar una excepción en caso de **SetPrintOptions** se produce un error. Puede especificar **True** (continuar) o **False** (producir una excepción).  
  
-   **SetRepeatOptions**: le permite establecer las opciones de repetición para el programa simultáneo antes de enviar la solicitud. **SetRepeatOptions** toma las siguientes opciones como parámetros:  
  
    -   **RepeatTime**: indica la hora del día para repetir las solicitudes simultáneas.  
  
    -   **RepeatInterval**: este parámetro solo es aplicable cuando **RepeatTime** es NULL. Indica el intervalo entre los reenvíos de la solicitud. Use esta opción junto con **RepeatUnit** para especificar el tiempo entre los reenvíos.  
  
    -   **RepeatUnit**: este parámetro solo es aplicable cuando **RepeatTime** es NULL. La unidad de tiempo que se utiliza junto con **RepeatInterval** para especificar el tiempo entre los reenvíos de la solicitud. Puede especificar **minutos**, **horas**, **días** o **meses**.  
  
    -   **RepeatType**: este parámetro solo es aplicable cuando **RepeatTime** es NULL. Indica si el intervalo de repetición se aplica después del "inicio" de una ejecución de solicitudes simultáneas o después del "final" de una ejecución de solicitudes simultáneas.  
  
    -   **RepeatEndTime**: indica la fecha y hora para detener volver a enviar las solicitudes simultáneas.  
  
    -   **ContinueOnFail**: indica si el envío de solicitudes simultáneas debe continuar o iniciar una excepción en caso de **SetRepeatOptions**. Puede especificar **True** (continuar) o **False** (producir una excepción).  
  
 **Parámetros de tipo simple**  
  
-   **Descripción**: descripción de las solicitudes simultáneas.  
  
-   **StartTime**: indica el tiempo en el que las solicitudes simultáneas deben iniciar su ejecución.  
  
## <a name="getstatus-operation"></a>Operación Get_Status  
 La operación estándar, Get_Status, devuelve la fase/estado de la solicitud y el mensaje de finalización de un programa simultáneo. Esta operación toma el identificador de solicitud de un programa simultáneo (**RequestID**) como entrada y, a continuación, devuelve la siguiente información:  
  
-   **Fase**: la fase de solicitud fácil de usar de FND_LOOKUPS.  
  
-   **Estado de**: el estado de la solicitud fácil de usar de FND_LOOKUPS.  
  
-   **DevPhase**: la fase de solicitud como una cadena que se puede usar para comparaciones de lógica de programa.  
  
-   **DevStatus**: el estado de la solicitud como una cadena que se puede usar para comparaciones de lógica de programa.  
  
-   **Mensaje**: el mensaje de finalización si se ha completado la solicitud.  
  
## <a name="waitforrequest-operation"></a>Operación Wait_For_Request  
 La operación estándar, Wait_For_Request, espera para la finalización de la solicitud y, a continuación, devuelve la fase/estado de la solicitud y el mensaje de finalización. Esta operación toma el identificador de solicitud de un programa simultáneo (**RequestID**), el número de segundos que deben transcurrir entre comprobaciones (**intervalo**) y el tiempo máximo en segundos de espera para finalización (de la solicitud **MaxWait**) como parámetros de entrada y, a continuación, devuelve la misma información que en la operación de Get_Status.  
  
## <a name="submitrequest-operation"></a>Operación Submit_Request  
 La operación estándar, Submit_Request, envía una solicitud simultánea para el procesamiento por un administrador simultáneo. Si la solicitud se completa correctamente, esta operación devuelve el identificador de solicitudes simultáneas. En caso contrario, devuelve "0".  
  
 La operación de Submit_Request tiene seis parámetros estándares: tres de tipo simple de tipo complejo. Además de estos parámetros, también toma los argumentos del programa simultáneo como una matriz de cadena.  
  
 **Parámetros de tipo complejo**  
  
 Realiza la operación de Submit_Request **SetOptions**, **SetPrintOptions**, y **SetRepeatOptions** como parámetros de entrada. Para obtener información acerca de estos parámetros, consulte [ &lt;Concurrent_Program_Name&gt; operación](#Concurrent) anteriormente en esta sección.  
  
 **Parámetros de tipo simple**  
  
-   **Programa**: nombre corto del programa simultáneo para el que se debe enviar la solicitud.  
  
-   **Descripción**: descripción de las solicitudes simultáneas.  
  
-   **StartTime**: la hora a la que las solicitudes simultáneas deben iniciar su ejecución.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)