---
title: Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cf3430d-12e9-437c-b398-d978faa4da2b
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 103a5f8c84b57693dd8f19d47d2b94d5e26256d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217324"
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-service-model"></a>Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF
[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]Proporciona un modelo de programación que llama el modelo de servicio WCF para conectarse a la [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]. El modelo de servicio se ha agregado a WCF para resolver, en parte, algunas de las limitaciones del modelo de programación del canal WCF.  
  
 El modelo de servicio WCF usa los paradigmas familiares de .NET para ocultar las complejidades de intercambio de mensajes SOAP a través de un canal. El modelo de servicio realiza esta simplificación a leer todo el mensaje SOAP en la memoria antes de copiar la información en estructuras de datos. NET. Cargar mensajes largos en la memoria puede no resultar práctico en algunas aplicaciones. En estos casos, los desarrolladores deben utilizar el modelo de canal WCF. Para obtener más información acerca de cómo utilizar el modelo de canal WCF, vea [desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md).  
  
 En el nivel más bajo, el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] presenta el modelo de canal WCF en el que los clientes invocar operaciones en un servicio mediante el intercambio de mensajes SOAP a través de un canal establecido entre los extremos de cliente y el servicio. El modelo de canal WCF expone los tipos de datos y métodos que permiten trabajar directamente en la arquitectura de canal WCF. El modelo de canal WCF proporciona control directo sobre el contenido de los mensajes SOAP que crea y sobre la forma tanto la aplicación y la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] consumirlos. Sin embargo, crear mensajes SOAP con formato correcto para enviar a través de un canal y validar los mensajes de respuesta devueltos pueden ser una tarea detallada y exigente.  
  
 El modelo de servicio WCF usa las clases de proxy para invocar operaciones en un servicio de destino o para operaciones de recepción de un cliente. La [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone Oracle E-Business Suite como un servicio WCF en el que se pueden invocar operaciones.  
  
-   La clase de proxy que se utiliza para invocar operaciones en un servicio de destino se denomina una clase de cliente WCF. Esta clase modela las operaciones expuestas por un servicio como métodos de .NET con parámetros fuertemente tipados. Mediante el modelo de servicio WCF, puede invocar las operaciones expuestas por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] como métodos de .NET en el cliente de WCF. Para obtener más información acerca de los clientes WCF, vea [información general sobre el cliente de WCF](https://msdn.microsoft.com/library/ms735103.aspx).
  
 Puede utilizar cualquiera de las siguientes herramientas para generar una clase de cliente WCF y código auxiliar de los metadatos del servicio asociado que la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone:  
  
-   **La herramienta de utilidad de metadatos de ServiceModel (svcutil.exe)**, que se incluye con WCF.  
  
-   **El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** , que se incluye con la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] y se integra con la [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] experiencia de diseño. Esta herramienta presenta una interfaz estándar de Microsoft Windows que proporciona una exploración y capacidades en las operaciones que expone el adaptador de búsqueda eficaces. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio de WCF para los artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).  
  
## <a name="in-this-section"></a>En esta sección  
 Los temas siguientes proporcionan información sobre cómo desarrollar aplicaciones que usan el modelo de servicio WCF:  
  
-   [Información general sobre el modelo de servicio WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [Metadatos y el modelo de servicio WCF con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/metadata-and-the-wcf-service-model-with-oracle-e-business-suite.md)  
  
-   [Generar un cliente WCF o un contrato de servicio WCF para los artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)  
  
-   [Configurar un enlace de cliente de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)  
  
-   [Realización de Insert, Update, Delete o Select operaciones en tablas de interfaz y vistas que usan el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)  
  
-   [Completar las operaciones en tablas con tipos de datos de gran tamaño en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md)  
  
-   [Invocar programas simultáneos en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [Invocar conjuntos de solicitudes en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [Realizar ExecuteReader, ExecuteScalar u operaciones ExecuteNonQuery en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-executenonquery-in-oracle-ebs-with-a-wcf-service.md)  
  
-   [Sondeo Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [Recibir notificaciones de cambio de base de datos Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-the-wcf-service-model.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)