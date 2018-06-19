---
title: Crear TIBCO EMS recibe artefactos | Documentos de Microsoft
description: Crear el puerto de recepción y establecer las propiedades de transporte para usar el adaptador de TIBCO Enterprise Message Service en el servidor BizTalk Server
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1307e3c-0237-4f19-a642-58e694fe95d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5810dc012c7aa5dcc2fbdfcecd9d59d066ced7
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015379"
---
# <a name="create-tibco-ems-receive-artifacts"></a>Crear TIBCO EMS artefactos de recepción

## <a name="overview"></a>Información general
El receptor TIBCO Enterprise Message Service es un servicio de escucha que registra una cola o tema particular y recibe los mensajes relacionados. El adaptador de BizTalk para TIBCO Enterprise Message Service se registra primero con TIBCO Enterprise Message Service, mediante la apertura de una nueva sesión y, después, continúa realizando el sondeo para recibir mensajes. En esta sección se explica cómo configurar el puerto de recepción para conectarse a TIBCO Enterprise Message Service y cómo incluir XML en la orquestación para interactuar con TIBCO EMS en tiempo de ejecución.  

## <a name="create-a-receive-port"></a>Crear un puerto de recepción  
  
1.  En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación.  
  
2.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puertos de recepción unidireccionales**.  
  
3.  En el **propiedades de puerto de recepción** ventana, en la **General** página, realice lo siguiente:  
  
    1.  En el **nombre** , escriba `ReceiveFromTIBCOEMS`.  
  
    2.  En el **autenticación** cuadro del grupo, especifique cómo se administran los mensajes al utilizar la autenticación.  
  
    3.  Seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación.  
  
4.  En el **ubicaciones de recepción** página, realice lo siguiente:  
  
    1.  Haga clic en **Nueva**.  
  
    2.  En el **ubicaciones de recepción** ventana, en la **General** página, escriba el **nombre** de la ubicación de recepción.  
  
    3.  Desde el **tipo** lista desplegable, seleccione el tipo de transporte y desde el **controlador de recepción** lista desplegable, seleccione la dirección de transporte.  
  
    4.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización de recepción.  
  
    5.  En el **programación** página, seleccione la **fecha de inicio** y **fecha de finalización** para restringir la recepción de documentos.  
  
    6.  Seleccione el **habilitar ventana de servicio** casilla de verificación.  
  
    7.  Haga clic en **Aceptar**.  
  
5.  En el **asignaciones de entrada** , seleccione las asignaciones de entrada para transformar documentos en el puerto seleccionado.  
  
6.  En el **seguimiento** página, seleccione el seguimiento de cuerpos de mensaje y el seguimiento de propiedades de mensaje deseado.  
  
7.  Haga clic en **Aceptar**.  

## <a name="set-the-receive-port-transport-properties"></a>Establecer propiedades de transporte del puerto de recepción
Ubicación de recepción para un sistema TIBCO Enterprise Message (EMS) la **URL** y **Target Namespace** para el sistema TIBCO EMS son los únicos valores de configuración necesarios.    
 
1.  Expanda el **definición del sistema** y escriba toda la información necesaria para la conexión al servidor TIBCO EMS.  
  
2.  Expanda **control de mensajes** y escriba toda la información necesaria.  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |**Selector de mensajes**|Los mensajes únicamente se reciben si esta cadena se evalúa en True con el mensaje en el destino.<br /><br /> Permite que el puerto de recepción recupere únicamente los mensajes que contienen propiedades de encabezado que coincidan con la expresión descrita en este campo.<br /><br /> La sintaxis de los selectores de mensajes se basa en un subconjunto de la sintaxis de expresiones condicionales de SQL92. La sintaxis se describe completamente en la guía del usuario de TIBCO EMS.<br /><br /> Por ejemplo, si un mensaje contiene un nombre de propiedad de encabezado NewsType, un puerto de recepción únicamente puede recuperar los elementos que sean de tipo Sports o Editorial.|  
    |**Número de reintentos**|El número de reintentos para el transporte. Valor predeterminado es 0.|  
    |**Intervalo de reintento**|El período de tiempo que el adaptador espera antes de iniciar un reintento. El valor predeterminado es cinco minutos.|  
  
3.  Expanda el **definición de conexión de servidor** y escriba toda la información necesaria.  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |**Destino**|Configuración obligatoria. Define el nombre y tipo de destino. Define la cola o tema con el formato siguiente: Queue[queue.name] o Topic[topic.name].|  
    |**Número de puerto**|Puerto en que escucha el servidor TIBCO EMS.|  
    |**Nombre de servidor**|Configuración obligatoria. Nombre del sistema que hospeda el servidor TIBCO EMS.|  
  
4.  Proporcione credenciales mediante el inicio de sesión único (SSO).  
  
     Se pueden usar dos métodos para tener acceso al sistema TIBCO EMS. Puede usar las credenciales (parámetros de nombre de usuario y contraseña) o el inicio de sesión único.  
  
    -   Seleccione **Sí** en **usar SSO** usar Single Sign-On.  
  
    -   Seleccione una aplicación afiliada en la lista.  
  
         Una aplicación afiliada, creada por herramientas de inicio de sesión único empresarial, representa una aplicación como TBCO EMS. El adaptador de Microsoft BizTalk para TIBCO EMS usa las credenciales de un usuario de la aplicación. Estas credenciales se recuperan de la base de datos de SSO del sistema de servidor para una aplicación afiliada determinada.  
  
         Para obtener más información acerca de cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications5.md).  
  
5.  Expanda **las credenciales de usuario** y escriba la **nombre de usuario** y **contraseña** para tener acceso al servidor TIBCO EMS.  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |`Password`|La contraseña del usuario que se usa para comunicar con un demonio TIBCO EMS.<br /><br /> Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para TIBCO EMS pueda comunicarse con un daemon TIBCO EMS.|  
    |`User Name`|Nombre de un usuario que se usa para comunicar con un demonio TIBCO EMS.<br /><br /> Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para TIBCO EMS pueda comunicarse con un daemon TIBCO EMS.|  
  
6.  Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**. 

## <a name="next-steps"></a>Pasos siguientes
[Propiedades de contexto del mensaje de TIBCO EMS](../core/message-context-properties-in-biztalk-server.md)