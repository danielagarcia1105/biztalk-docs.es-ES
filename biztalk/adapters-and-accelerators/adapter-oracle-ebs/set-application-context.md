---
title: Establecer el contexto de aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9697155-70c0-4173-80d2-d02d103c397b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a512f2b3e198d496390bdc462af073bf05c1668
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004237"
---
# <a name="set-application-context"></a>Establecer el contexto de aplicación
En [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)], Establece el contexto de aplicación es obligatorio para algunos artefactos de Oracle E-Business Suite (tablas, vistas de interfaz, programas simultáneos y conjuntos de solicitudes) para poder realizar operaciones en ellos. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no permite realizar operaciones en estos artefactos hasta que haya establecido el contexto de la aplicación. Sin embargo, los artefactos en la base de datos de Oracle subyacente, es depende del usuario si desea establecer el contexto de la aplicación o no.  
  
## <a name="what-is-application-context"></a>¿Qué es el contexto de la aplicación  
 Contexto de la aplicación es un conjunto de elementos asociados con un artefacto en Oracle E-Business Suite que implementa las preferencias del usuario y el control de acceso en el artefacto. Contexto de la aplicación consta de los siguientes elementos:  
  
- **Nombre de usuario**: un usuario que puede conectarse a Oracle E-Business Suite.  
  
- **Responsabilidad**: una responsabilidad es un nivel de acceso en Oracle E-Business Suite que permite a los usuarios tener acceso a solo los datos y funciones que son adecuadas para sus funciones en una organización. Responsabilidades pueden permitir el acceso a una aplicación específica, operativo unidades, conjunto de libros y una lista restringida de windows, las funciones y otras responsabilidades. En virtud de la asignación de las responsabilidades para un usuario, puede conceder o restringir el acceso del usuario en Oracle E-Business Suite.  
  
- **Id. de organización**: Oracle E-Business Suite admite la configuración de seguridad de varias organizaciones. Estas organizaciones diferentes se identifican por un valor de Id. de organización, en la columna Org_ID de la tabla de Oracle E-Business Suite que almacena información acerca de estas organizaciones. En virtud de asignar la responsabilidad de una organización o seleccionar explícitamente una organización, puede conceder o restringir el acceso de un usuario a una organización.  
  
  Para obtener más información acerca de la responsabilidad, varias organizaciones y los Id. de organización en Oracle E-Business Suite, busque el [centro de Ayuda de Oracle](http://docs.oracle.com).  
  
## <a name="setting-application-context"></a>Establece el contexto de aplicación  
 Como el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se conecta a la base de datos subyacente en Oracle E-Business Suite, contexto de la aplicación para los artefactos de Oracle E-Business Suite no están establecidos o inicializados en el adaptador. Puede inicializar o establecer el contexto de la aplicación para estos artefactos en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mediante el uso de las siguientes acciones:  
  
- **Propiedades de enlace**: el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone las siguientes propiedades de enlace para establecer el contexto de la aplicación: **OracleEBSOrganizationId**, **OracleUserName**,  **OraclePassword**, **OracleEBSResponsibilityKey**, **OracleEBSResponsibilityName**, y **ApplicationShortName**. No es necesario especificar valores para todas estas propiedades de enlace establecer el contexto de la aplicación para distintos artefactos. Para obtener información acerca de las propiedades de enlace necesarios para el contexto de la aplicación de configuración de un artefacto, consulte [propiedades de enlace de la configuración de contexto para distintos artefactos de la aplicación](#Binding) más adelante en este tema.  
  
- **Las propiedades de contexto del mensaje**: el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone las siguientes propiedades de contexto de mensaje para establecer el contexto de la aplicación: **ApplicationShortName**, **OrganizationID** , **ResponsibilityKey**, y **ResponsibilityName**. Para especificar el nombre de usuario y la contraseña, debe usar las propiedades de enlace. Para obtener información sobre cómo establecer el contexto de la aplicación mediante las propiedades de contexto de mensaje, vea [configurar las propiedades del mensaje utilizando aplicación contexto contexto](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md).  
  
> [!IMPORTANT]
>  El valor especificado para el **OracleEBSResponsibilityKey** enlaza la propiedad invalida el valor de la **OracleEBSResponsibilityName** enlaza la propiedad. De forma similar, el valor especificado para el **ResponsibilityKey** propiedad de contexto de mensaje invalida el valor especificado para el **ResponsibilityName** propiedad de contexto del mensaje.  
  
### <a name="precedence-order-binding-properties-vs-message-context-properties"></a>Orden de prioridad (propiedades de enlace frente a las propiedades de contexto de mensaje)  
 Si establece el contexto de la aplicación mediante las propiedades de enlace y las propiedades de contexto de mensaje, los valores especificados para las propiedades de contexto de mensaje tiene prioridad y reemplaza los valores especificados para las propiedades de enlace. Pero, por ejemplo, si especifica el nombre corto de la aplicación como una propiedad de contexto de mensaje y el resto como propiedades de enlace, solo el valor para el nombre corto de la aplicación procede de la propiedad de contexto de mensaje y el resto se toman del enlace relevante Propiedades.  
  
 **Orden de prioridad para el nombre corto de la aplicación**  
  
 Al establecer el contexto de la aplicación, se usa el nombre corto de la aplicación en el siguiente orden de prioridad (de mayor a menor):  
  
- El nombre corto de aplicación especificado en el **ApplicationShortName** propiedad de contexto del mensaje.  
  
- Nombre corto de la aplicación especificado en la acción SOAP (para tablas, vistas de interfaz, programas simultáneos y solo los conjuntos de solicitud).  
  
- El nombre corto de aplicación especificado en el **ApplicationShortName** enlaza la propiedad.  
  
  Sin embargo, para las tablas, vistas de interfaz, programas simultáneos y conjuntos de solicitudes, en este orden de prioridad solo es aplicable al establecer el contexto de la aplicación. Para identificar las tablas, vistas de interfaz, programas simultáneos y solicitud de conjuntos, la aplicación se usa el nombre corto de la acción SOAP.  
  
  **Orden de prioridad para el nombre de la responsabilidad y la clave de responsabilidad**  
  
  Al establecer el contexto de la aplicación, la clave de responsabilidad y el nombre de la responsabilidad se usan en el siguiente orden de prioridad (de mayor a menor):  
  
- La clave de responsabilidad especificada en el **ResponsibilityKey** propiedad de contexto del mensaje.  
  
- El nombre de responsabilidad especificado en el **ResponsibilityName** propiedad de contexto del mensaje.  
  
- La clave de responsabilidad especificada en el **OracleEBSResponsibilityKey** enlaza la propiedad.  
  
- El nombre de responsabilidad especificado en el **OracleEBSResponsibilityName** enlaza la propiedad.  
  
> [!TIP]
>  **¿Por qué usar propiedades de contexto de mensaje a través de propiedades para establecer el contexto de la aplicación de enlace?** Si establece el contexto de la aplicación mediante las propiedades de enlace, el WCF-Custom puerto de envío para el Oracle E-Business adaptador puede utilizarse solo para el Id. de organización específica, la responsabilidad y la aplicación que ha especificado para las propiedades de enlace. Por el contrario, si usa la propiedad de contexto de mensaje puede configurar un puerto de envío WCF-Custom "genérico" y establecer el contexto de la aplicación en el nivel de mensaje.  
  
### <a name="setting-application-context-for-interface-tables-interface-views-concurrent-programs-and-request-sets-mandatory"></a>Establecer el contexto de la aplicación para tablas, vistas de interfaz, programas simultáneos y conjuntos de solicitudes (obligatorio)  
 Debe establecer el contexto de la aplicación antes de realizar operaciones en tablas, vistas de interfaz, programas simultáneos y solicitud se establece [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para ello, tendrá que proporcionar los valores adecuados para las propiedades de enlace o las propiedades de contexto de mensaje como se especificó anteriormente.  
  
> [!IMPORTANT]
>  No se puede realizar operaciones en tablas, vistas de interfaz, programas simultáneos y solicitud de establece a menos que se ha establecido los valores adecuados para las propiedades de enlace necesaria o el mensaje de las propiedades de contexto.  
  
### <a name="setting-application-context-for-plsql-apis-procedures-functions-tables-and-views"></a>Establece el contexto de aplicación de API de PL/SQL, procedimientos, funciones, tablas y vistas  
  
- **Las API de PL/SQL**: el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone las API de PL/SQL asociados con la base de datos de Oracle, así como la aplicación de Oracle E-Business Suite. Aunque es opcional establecer el contexto de la aplicación para las API de PL/SQL asociado con la base de datos de Oracle, es obligatorio para establecer el contexto de la aplicación para las API de PL/SQL asociado a la aplicación de Oracle E-Business Suite.  
  
- **Procedimientos y funciones**: no es obligatorio para establecer el contexto de la aplicación para realizar operaciones en los procedimientos y funciones en la base de datos de Oracle.  
  
- **Las tablas y vistas**: no es obligatorio para establecer el contexto de la aplicación para realizar operaciones en tablas y vistas en la base de datos de Oracle. Sin embargo, para la aplicación personalizada de Oracle E-Business Suite, los usuarios pueden o no pueden registrar las tablas de base de datos como tablas de interfaz. Si una tabla de base de datos no está registrada como una tabla de interfaz, se mostrará junto con las tablas de base de datos en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Dado que estas tablas están asociadas a una aplicación de Oracle E-Business, para cualquier operación en estas tablas debe establecer el contexto de la aplicación.  
  
  Para establecer el contexto de la aplicación para estos artefactos, debe proporcionar los valores adecuados para las propiedades de enlace o las propiedades de contexto de mensaje como se especificó anteriormente.  
  
### <a name="setting-application-context-for-poll-executenonquery-executereader-executescalar-and-composite-operations"></a>Establecer el contexto de la aplicación para el sondeo, ExecuteNonQuery, ExecuteReader, ExecuteScalar y operaciones compuestas  
 Aparte de los artefactos, también puede establecer el contexto de la aplicación para realizar diversas operaciones que se realizan en estos artefactos.  
  
-   Para establecer el contexto de la aplicación para la operación de sondeo, solo sirve las propiedades de enlace según lo especificado anteriormente. Para el contexto de la aplicación de configuración, debe proporcionar los valores adecuados para las propiedades de enlace que son aplicables para el artefacto en el que se realiza la operación de sondeo. Por ejemplo, si se realiza la operación de sondeo en una tabla de interfaz, a continuación, debe especificar valores para las propiedades de enlace para la tabla de interfaz.  
  
-   Para establecer el contexto de la aplicación para las operaciones ExecuteNonQuery, ExecuteReader y ExecuteScalar, debe proporcionar los valores adecuados para las propiedades de enlace o el mensaje de las propiedades de contexto como se especificó anteriormente. Para el contexto de la aplicación de configuración para estas operaciones, debe proporcionar los valores adecuados para las propiedades de enlace o el mensaje de las propiedades de contexto que son aplicables para el artefacto en el que se realizan las operaciones.  
  
-   Para establecer el contexto de la aplicación para operaciones compuestas, debe proporcionar los valores adecuados para las propiedades de enlace o las propiedades de contexto de mensaje como se especificó anteriormente. Para el contexto de la aplicación de configuración para operaciones compuestas, debe proporcionar los valores adecuados para las propiedades de enlace o el mensaje de las propiedades de contexto que se aplican para las operaciones individuales. Por ejemplo, si una operación compuesta contiene dos operaciones: uno en la tabla de interfaz y la otra en la base de datos de tabla, debe especificar los valores de las propiedades de enlace o las propiedades de contexto de mensaje para la tabla de interfaz, así como el enlace las propiedades o las propiedades de contexto de mensaje para la tabla de base de datos.  
  
    > [!IMPORTANT]
    >  Para todas estas operaciones, es obligatorio para establecer el contexto de la aplicación si la operación se realiza en un artefacto en Oracle E-Business Suite (tabla de interfaz, vista de interfaz, programas simultáneos o conjuntos de solicitudes). Si la operación se realiza en un artefacto de la base de datos subyacente, no es obligatorio para establecer el contexto de la aplicación. Por ejemplo, si va a realizar la operación de sondeo en una tabla de interfaz, es obligatorio para establecer el contexto de la aplicación, mientras que si se realiza la operación de sondeo en una tabla, no es obligatorio para establecer el contexto de la aplicación.  
  
## <a name="setting-the-language-for-performing-operations"></a>Establecer el idioma de la realización de operaciones  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es compatible con la característica de compatibilidad con varios idiomas (MLS) de Oracle E-Business Suite, y le permite especificar un idioma al realizar las operaciones. Expone el adaptador el **lenguaje** enlaza la propiedad en el **MlsSettings** enlazar la propiedad y el **lenguaje** para especificar un idioma para la propiedad del contexto del mensaje realizar operaciones.  
  
 El valor especificado para el **lenguaje** propiedad de contexto de mensaje invalida el valor de la **lenguaje** enlaza la propiedad en el **MlsSettings** enlaza la propiedad. Para obtener más información sobre la **MlsSettings** enlaza la propiedad, vea [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
##  <a name="Binding"></a> Propiedades de enlace para establecer el contexto de la aplicación para distintos artefactos  
 En la tabla siguiente proporciona información sobre las propiedades de enlace para el que debe especificar los valores adecuados para establecer el contexto de la aplicación para distintos artefactos:  
  
|Artefactos|OracleEBSOrganizationId|OracleUserName|OraclePassword|OracleEBSResponsibilityKey<br />o Administrador de configuración de<br />OracleEBSResponsibilityName|ApplicationShortName|  
|---|---|---|---|---|---|  
|Tablas y vistas de interfaz|√*|√|√|√||  
|Programas simultáneos|√*|√|√|√||  
|Conjuntos de solicitudes|√*|√|√|√||  
|API de PL/SQL|√*|√|√|√|√|  
|Procedimientos y funciones|√*|√|√|√|√|  
|Tablas y vistas|√*|√|√|√|√|  
  
 **√\* = opcional**  
  
> [!IMPORTANT]
> - El valor predeterminado de la **OracleEBSOrganizationId** enlaza la propiedad (opcional) es null. Si especifica un valor para el **OracleEBSOrganizationId** enlaza la propiedad, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] el ORG_ID de la sesión se establece en este valor al establecer el contexto de la aplicación.  
>   -   El valor especificado para el **OracleEBSResponsibilityKey** enlaza la propiedad invalida el valor especificado para el **OracleEBSResponsibilityName** enlaza la propiedad.  
  
 Para obtener información detallada sobre cada una de estas propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)