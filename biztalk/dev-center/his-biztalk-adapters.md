---
title: Adaptadores de BizTalk incluidos con Host Integration Server | Documentos de Microsoft
description: "Información general de los adaptadores de BizTalk para aplicaciones de Host, archivos de host, DB2 y WebSphere MQ incluido con su"
author: MandiOhlinger
manager: anneta
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.author: mandia
ms.openlocfilehash: 26f2bf48c9a1268aace041776ff3895c8f3b3aa5
ms.sourcegitcommit: 75d35f6f230f0846c29a4b146c6d5b074e60b13c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2017
---
# <a name="biztalk-adapters-for-host-systems"></a>Adaptadores de BizTalk para sistemas host


## <a name="biztalk-adapter-for-host-applications"></a>Adaptador de BizTalk para aplicaciones Host

El adaptador de Microsoft BizTalk para aplicaciones Host está diseñado para que BizTalk Server. Se basa en tecnología de Microsoft Transaction Integrator (TI) para el procesamiento de Windows-Initiated, que permite el acceso de cliente eficaz a existente IBM mainframe zSeries (CICS e IMS) o programas de servidor de nivel intermedio iSeries (RPG). 

Las herramientas de diseño de TI se integran con Visual Studio y las soluciones de BizTalk Server, permitiendo a los desarrolladores de TI sean altamente productivos al definir al proxy de cliente y crear el esquema XSD. Para los administradores de BizTalk Server, el Administrador de TI existentes, complemento Microsoft Management Console (MMC), se ha mejorado para mejorar la compatibilidad y soporte técnico de los escenarios de implementación de soluciones de BizTalk Server remotos necesarios.

Vea [el adaptador de BizTalk para aplicaciones Host](https://msdn.microsoft.com/library/dn148497(BTS.80).aspx). 

## <a name="biztalk-adapter-for-host-files"></a>Adaptador de BizTalk para los archivos de Host
El adaptador de Microsoft BizTalk para los archivos de Host es un adaptador de datos avanzados que permite a las organizaciones de TI obtener acceso e integrar información almacenada en sistemas de archivos de host, incluidos mainframe zSeries VSAM conjuntos de datos y de nivel intermedio iSeries archivos físicos. 

Herramientas de diseño de Visual Studio se utilizan dentro de una solución de BizTalk Server para definir una asignación de metadatos de los archivos se describe el programa host, que, a continuación, se exporta como XSD para su uso con el adaptador de BizTalk. La configuración de asistentes se integran en las herramientas de administración de BizTalk Server, permitiendo los profesionales de TI para definir los puertos de envío dinámico y estático y petición respuesta puertos de recepción, en función de un conjunto simplificado de comandos SQL (SELECT, INSERT, UPDATE, DELETE ). 

Este adaptador de BizTalk se basa en el proveedor de datos de Microsoft .NET Framework para los archivos de Host que SQL se asigna a los miembros y conjuntos de datos no relacionales de host. Esto facilita a los de programadores leer y escribir orígenes de datos de archivo de host.

Vea [el adaptador de BizTalk para archivos Host](https://msdn.microsoft.com/library/dn150042(BTS.80).aspx).

## <a name="biztalk-adapter-for-db2"></a>Adaptador de BizTalk para DB2
El adaptador de BizTalk de Microsoft para DB2 es un adaptador de base de datos relacional que permite a los profesionales de TI obtener acceso a datos vitales almacenados en servidores de base de datos de IBM DB2 en el host remoto informática plataformas, IBM mainframe zSeries y iSeries de nivel intermedio (DB2/400) e IBM DB2 Universal Database (UDB) en plataformas abiertas. 

Con comandos SQL estándar y un asistente de configuración integrada en herramientas de administración de BizTalk Server, los profesionales de TI pueden crear soluciones que leen y escriben a DB2 sin necesidad de programación de la base de datos. El adaptador de DB2, que se basa en el proveedor de datos de Microsoft .NET Framework para DB2, es compatible con una amplia gama de funciones, incluidos los puertos de envío dinámico y estático y de petición respuesta puertos de recepción.

Vea [el adaptador de BizTalk para DB2](https://msdn.microsoft.com/library/dn150160(BTS.80).aspx).

## <a name="biztalk-adapter-for-websphere-mq"></a>Adaptador de BizTalk para WebSphere MQ
El adaptador de Microsoft BizTalk para WebSphere MQ (basado en cliente) usa el cliente IBM WebSphere MQ (Base de cliente) y las API de IBM WebSphere MQ extendidos transaccional (cliente extendido-) para comunicarse con administradores de cola de MQSeries remoto. Permite que el adaptador de BizTalk Server para comunicarse directamente con los administradores de cola de MQSeries implementadas en sistemas operativos que no son de Windows, sin necesidad de implementar y administrar WebSphere MQ Server para Windows, para intercambiar mensajes con la línea de negocio de forma eficaz aplicaciones a través de la empresa. 

Cuando se usa con el cliente de Base, el adaptador proporciona procesamiento de mensajes no transaccionales, para garantizar la entrega de los mensajes. Es responsabilidad de la aplicación en el extremo receptor para controlar los mensajes duplicados. Cuando se usa con el cliente extendido, el adaptador proporciona procesamiento para garantizar la entrega de una vez y-solo-una vez de mensajes transaccional de mensajes.

Vea [el adaptador de BizTalk para WebSphere MQ](https://msdn.microsoft.com/library/dn191830(BTS.80).aspx).
