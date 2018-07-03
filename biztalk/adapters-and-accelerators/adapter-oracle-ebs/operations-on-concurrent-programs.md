---
title: Operaciones en programas simultáneos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbc40e4c-d5a1-4763-9683-09a744e5b656
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a07e1cb6597a90687865932fcd2d2ce7e0e476af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000004"
---
# <a name="operations-on-concurrent-programs"></a>Operaciones en programas simultáneos
Programas simultáneos en Oracle E-Business Suite se exponen como operaciones en [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].  Además de los programas simultáneos específicos para una aplicación de Oracle, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] también expone las siguientes tres operaciones estándares: Get_Status, Wait_For_Request y Submit_Request. Esto implica que si una aplicación de Oracle tiene dos programas simultáneos, se expondrán cinco operaciones: uno para cada programa simultáneo y tres para las operaciones estándar.  
  
 Para obtener información acerca de:  
  
- Examinar y buscar en programas simultáneos, consulte [examinar, buscar y obtener metadatos para operaciones de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  
  
- Cómo invocar programas simultáneos en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [invocar programas simultáneos en Oracle E-Business Suite mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md).  
  
> [!IMPORTANT]
>  Debe establecer el contexto de las aplicaciones para programas simultáneos en [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para poder realizar cualquier operación en programas simultáneos. Esto es porque el contexto de las aplicaciones de configuración facilita transacciones seguras en Oracle E-Business Suite estableciendo las preferencias del usuario (por ejemplo, la configuración de idioma, la organización y la responsabilidad) y el control de acceso de un artefacto. Para obtener información sobre el contexto de las aplicaciones y cómo configurarlo, consulte Establecer contexto de la aplicación[establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
 Las secciones siguientes proporcionan información acerca de las operaciones expuestas por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para programas simultáneos.  
  
##  <a name="Concurrent"></a> Operación < Concurrent_Program_Name >  
 Como se mencionó anteriormente, habrá tantas operaciones < Concurrent_Program_Name > como el número de programas simultáneos en una aplicación de Oracle. La operación < Concurrent_Program_Name > toma cinco parámetros estándares: tres de tipo complejo y dos de tipo simple.  
  
> [!NOTE]
>  Para los programas simultáneos que no exponen sus metadatos, el adaptador de Oracle E-Business expone 100 parámetros opcionales para cada uno de estos programas simultáneos. Para llamar correctamente a estos programas simultáneos, el usuario debe consultar la documentación de Oracle E-Business Suite para averiguar los parámetros de un programa simultáneo que requieren un valor y especificarlos, a continuación. Un ejemplo de este tipo de programa simultáneo es **importación de Journal** (nombre real: **GLLEZL**) en el **contabilidad** aplicación.  
  
 **Parámetros de tipo complejo**  
  
- **SetOptions**: le permite establecer opciones para el programa simultáneo antes de enviar la solicitud. SetOptions toma las siguientes opciones como parámetros:  
  
  -   **Implícita**: indica si se debe mostrar las solicitudes simultáneas en el formulario del usuario solicitudes simultáneas en Oracle E-Business Suite. Puede especificar cualquiera de los siguientes cuatro valores: **No**, **Sí**, **Error** o **advertencia**. Especificar **n**hace que las solicitudes que se mostrará en el formulario del usuario solicitudes simultáneas en Oracle E-Business Suite. Especificar **Sí** implica que se puede ver la solicitud solo desde el formulario de solicitudes simultáneas con privilegios del administrador del sistema. Especificar **Error** hace que la solicitud que se mostrará en el formulario de solicitudes simultáneas del usuario solo si se produce un error. Especificar **advertencia** hace que la solicitud para mostrar en if solo del formulario de solicitudes simultáneas del usuario que hay una advertencia o un error.  
  
  -   **Protegido**: indica si la solicitud simultánea está protegida frente a las actualizaciones realizadas con el formulario de solicitudes simultáneas en Oracle E-Business Suite. Puede especificar **Sí** (protegido) o **No** (sin protección).  
  
  -   **Lenguaje**: indica el idioma de la compatibilidad de idioma nacional (NLS). Si se especifica ningún valor, el valor predeterminado es el idioma actual.  
  
  -   **Territorio**: indica el territorio de lenguaje. Si se especifica ningún valor, el valor predeterminado es el territorio de lenguaje actual.  
  
  -   **ContinueOnFail**: indica si el envío de solicitudes simultáneas debe continuar o producir una excepción en caso de **SetOptions** se produce un error. Puede especificar **True** (continuar) o **False** (inicia una excepción).  
  
- **SetPrintOptions**: le permite establecer las opciones de impresión para el programa simultáneo antes de enviar la solicitud. SetPrintOptions toma las siguientes opciones como parámetros:  
  
  -   **Impresora**: indica el nombre de la impresora que se debe enviar la salida de solicitudes simultáneas. No se puede invalidar esta opción de impresión si ya está establecido en el formulario de programas simultáneos en Oracle E-Business Suite.  
  
  -   **Estilo**: indica el estilo de impresión que se usa para imprimir la salida de solicitudes simultáneas. Por ejemplo, puede especificar la orientación (**horizontal** o **vertical**). Si el estilo de impresión ya está establecido en el formulario de programas simultáneos en Oracle E-Business Suite y el **estilo requerido** casilla de verificación está activada, no se puede invalidar esta opción de impresión.  
  
  -   **Copias**: indica el número de copias que desea imprimir de la salida de solicitudes simultáneas.  
  
  -   **SaveOutput**: indica si se deben guardar el archivo de salida. Puede especificar **Sí** o **No**.  
  
  -   **PrintTogether**: aplicable solo a esas solicitudes que contienen las subcarpetas de las solicitudes. Indica cómo se imprime la salida de solicitudes secundarias. Si especifica **Y**, se imprime la salida de solicitudes secundarias solo después de que finalizan todas las solicitudes secundarias. Si especifica **N**, la salida de cada solicitud secundaria se imprime tal y como se complete.  
  
  -   **ContinueOnFail**: indica si el envío de solicitudes simultáneas debe continuar o producir una excepción en caso de **SetPrintOptions** se produce un error. Puede especificar **True** (continuar) o **False** (inicia una excepción).  
  
- **SetRepeatOptions**: le permite establecer las opciones de repeticiones para el programa simultáneo antes de enviar la solicitud. **SetRepeatOptions** toma las siguientes opciones como parámetros:  
  
  -   **RepeatTime**: indica la hora del día a repetir la solicitud simultánea.  
  
  -   **RepeatInterval**: este parámetro solo es aplicable cuando **RepeatTime** es NULL. Indica el intervalo entre reenvíos de la solicitud. Use esta opción junto con **RepeatUnit** para especificar el tiempo entre reenvíos.  
  
  -   **RepeatUnit**: este parámetro solo es aplicable cuando **RepeatTime** es NULL. La unidad de tiempo que se usa junto con **RepeatInterval** para especificar el tiempo entre reenvíos de la solicitud. Puede especificar **minutos**, **horas**, **días** o **meses**.  
  
  -   **RepeatType**: este parámetro solo es aplicable cuando **RepeatTime** es NULL. Indica si el intervalo de repetición se aplica después del "inicio" de una ejecución de solicitudes simultáneas o después de "final" de una ejecución de solicitudes simultáneas.  
  
  -   **RepeatEndTime**: indica la fecha y hora para detener reenviando la solicitud simultánea.  
  
  -   **ContinueOnFail**: indica si el envío de solicitudes simultáneas debe continuar o producir una excepción en caso de **SetRepeatOptions**. Puede especificar **True** (continuar) o **False** (inicia una excepción).  
  
  **Parámetros de tipo simple**  
  
- **Descripción**: descripción de la solicitud simultánea.  
  
- **StartTime**: indica la hora en que las solicitudes simultáneas deben iniciar su ejecución.  
  
## <a name="getstatus-operation"></a>Operación Get_Status  
 La operación estándar, Get_Status, devuelve el estado/fase de la solicitud y el mensaje de finalización de un programa simultáneo. Esta operación utiliza el identificador de solicitud de un programa simultáneo (**RequestID**) como entrada y, a continuación, devuelve la siguiente información:  
  
-   **Fase**: la fase de solicitud fácil de usar desde FND_LOOKUPS.  
  
-   **Estado**: el estado de solicitud fácil de usar desde FND_LOOKUPS.  
  
-   **DevPhase**: la fase de solicitud como una cadena que se puede usar para comparaciones lógicas de programa.  
  
-   **DevStatus**: el estado de la solicitud como una cadena que se puede usar para comparaciones lógicas de programa.  
  
-   **Mensaje**: el mensaje de finalización si se ha completado la solicitud.  
  
## <a name="waitforrequest-operation"></a>Operación Wait_For_Request  
 La operación estándar, Wait_For_Request, espera la finalización de la solicitud y, a continuación, devuelve el estado/fase de la solicitud y el mensaje de finalización. Esta operación utiliza el identificador de solicitud de un programa simultáneo (**RequestID**), el número de segundos de espera entre comprobaciones (**intervalo**) y el tiempo máximo en segundos de espera para (de finalización la solicitud **MaxWait**) como parámetros de entrada y, a continuación, devuelve la misma información que en la operación Get_Status.  
  
## <a name="submitrequest-operation"></a>Operación Submit_Request  
 La operación estándar, Submit_Request, envía una solicitud simultánea para el procesamiento por un administrador simultáneo. Si la solicitud se completa correctamente, esta operación devuelve el identificador de solicitudes simultáneas. En caso contrario, devuelve "0".  
  
 La operación Submit_Request adopta seis parámetros estándares: tres de tipo simple de tipo complejo. Además de estos parámetros, también toma los argumentos del programa simultáneo como una matriz de cadena.  
  
 **Parámetros de tipo complejo**  
  
 La operación Submit_Request toma **SetOptions**, **SetPrintOptions**, y **SetRepeatOptions** como parámetros de entrada. Para obtener información acerca de estos parámetros, vea [ &lt;Concurrent_Program_Name&gt; operación](#Concurrent) anteriormente en esta sección.  
  
 **Parámetros de tipo simple**  
  
-   **Programa**: nombre corto del programa simultáneo para el que se debe enviar la solicitud.  
  
-   **Descripción**: descripción de la solicitud simultánea.  
  
-   **StartTime**: la hora en que las solicitudes simultáneas deben iniciar su ejecución.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)