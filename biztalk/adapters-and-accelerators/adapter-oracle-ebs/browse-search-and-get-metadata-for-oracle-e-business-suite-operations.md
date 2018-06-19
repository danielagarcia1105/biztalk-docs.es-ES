---
title: Examinar, buscar y obtener los metadatos de las operaciones de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05a0656c-84d0-4f25-9571-90a9df587b8c
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a26b13ddef6efe9214e7d889d5d8e02d2f1505cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217796"
---
# <a name="browse-search-and-get-metadata-for-oracle-e-business-suite-operations"></a>Examinar, buscar y obtener los metadatos de las operaciones de Oracle E-Business Suite
Esta sección proporciona información sobre cómo usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] y [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. Mediante el uso de estos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes, puede:  
  
-   Buscar operaciones recuperar los metadatos.  
  
-   Buscar operaciones recuperar los metadatos.  
  
-   Agregar esquemas de mensaje para las operaciones seleccionadas y el puerto de los archivos de configuración de enlace para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyecto cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
-   Agregar una clase de cliente WCF o un contrato de servicio WCF (interfaz) para operaciones seleccionadas y un archivo de configuración (app.config) a un proyecto de programación de BizTalk no cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
## <a name="how-is-the-metadata-categorized"></a>¿Cuál es la clasifica por categorías de metadatos?  
 El [!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] proporciona tres vistas diferentes de los artefactos disponibles en el servidor de Oracle E-Business Suite se conecta a:**vista basada en la aplicación**, **vista basada en el artefacto**y el **vista basada en el esquema**. ¿Por qué necesita tres vistas diferentes para el mismo conjunto de artefactos? La siguiente tabla se muestran los motivos por qué se debe usar una vista específica.  
  
|Ver|Cuando se utiliza|  
|----------|------------------------|  
|**Vista basada en la aplicación**|Esta vista está clasificada por los nombres de la aplicación de Oracle E-Business Suite. Utilice esta vista cuando se sabe que la aplicación que contiene los artefactos que desea trabajar.|  
|**Vista de artefacto**|Esta vista está clasificada por los artefactos de Oracle E-Business Suite. Utilice esta vista cuando se sabe qué artefacto de Oracle E-Business Suite que desee trabajar con pero no está seguro de qué aplicación al que pertenece el artefacto. Con esta visualización, puede buscar un artefacto específico en todas las aplicaciones de Oracle E-Business Suite.<br /><br /> La vista basada en el artefacto también enumera los artefactos de la base de datos de Oracle subyacente como API PL-SQL, tablas, vistas, funciones y procedimientos. Estos artefactos se clasifican en función del esquema al que pertenecen. Por lo tanto, otro uso de la vista basada en el artefacto es usar los artefactos que pertenecen a su esquema, así como los artefactos que pertenecen a otros esquemas. Esta vista también permite buscar artefactos en todos los esquemas.|  
|**Vista de esquema**|Esta vista está clasificada por los esquemas disponibles en la base de datos de Oracle subyacente. Utilice esta vista cuando se sabe qué esquema tiene los artefactos que desea trabajar. En esta vista, los artefactos tal y como se clasifica por categorías como API PL-SQL, procedimientos, funciones, tablas y vistas.|  
  
 Para obtener más información sobre cómo se clasifican los artefactos de Oracle E-Business Suite, consulte [conectarse a Oracle E-Business Suite en Visual Studio mediante el Asistente para agregar metadatos de adaptador](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md) otra razón clave para organizar los artefactos de vistas diferentes es la facilidad para buscar artefactos específicos. Para obtener más información sobre cómo busca artefactos, vea [búsqueda para las operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md).  
  
> [!IMPORTANT]
>  Los nodos se muestran según el URI que se especifique al establecer una conexión de conexión. Si especifica las credenciales que no tiene permisos en los artefactos de Oracle E-Business Suite, no puede usar los artefactos de la **vista basada en la aplicación**. Además, el **vista basada en el artefacto** no muestra los artefactos que pertenecen a Oracle E-Business Suite.  
  

  
## <a name="see-also"></a>Vea también  
 [Obtiene los metadatos para operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)