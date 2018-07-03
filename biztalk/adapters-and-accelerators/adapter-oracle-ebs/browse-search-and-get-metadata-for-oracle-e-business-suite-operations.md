---
title: Examinar, buscar y obtener metadatos para operaciones de Oracle E-Business Suite | Microsoft Docs
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
ms.openlocfilehash: 46588632c4444c5c38966cfc22fd75711d2af11a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996887"
---
# <a name="browse-search-and-get-metadata-for-oracle-e-business-suite-operations"></a>Examinar, buscar y obtener metadatos para operaciones de Oracle E-Business Suite
Esta sección proporciona información sobre cómo usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] y [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. Si se utilizan [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes, puede:  
  
- Buscar operaciones recuperar los metadatos.  
  
- Búsqueda de operaciones recuperar los metadatos.  
  
- Agregar esquemas de mensaje para operaciones seleccionadas y el puerto de los archivos de configuración de enlace a un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyecto cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
- Agregar una clase de cliente WCF o un contrato de servicio WCF (interfaz) para las operaciones seleccionadas y un archivo de configuración (app.config) a un proyecto de programación que no sean de BizTalk cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
## <a name="how-is-the-metadata-categorized"></a>¿Qué hay metadatos clasifica por categorías?  
 El [!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] ofrece tres vistas diferentes de los artefactos disponibles en el servidor de Oracle E-Business Suite se conecta a:**vista basada en la aplicación**, **vista basada en artefactos**y el **vista basada en esquema**. ¿Por qué necesita tres vistas diferentes para el mismo conjunto de artefactos? La siguiente tabla se enumeran los motivos por qué se debe usar una vista específica.  
  
|Ver|Cuando se usa|  
|----------|------------------------|  
|**Vista basada en la aplicación**|Esta vista está clasificada por los nombres de la aplicación de Oracle E-Business Suite. Use esta vista cuando se sabe que la aplicación que contiene los artefactos que desea trabajar.|  
|**Vista de artefacto**|Esta vista está clasificada por los artefactos de Oracle E-Business Suite. Use esta vista cuando sepa qué artefacto de Oracle E-Business Suite que desee trabajar con, pero no está seguro de qué aplicación el artefacto de pertenece a. Con esta visualización, puede buscar un artefacto específico en todas las aplicaciones de Oracle E-Business Suite.<br /><br /> La vista basada en artefactos también enumera los artefactos de la base de datos de Oracle subyacente, como API PL-SQL, tablas, vistas, funciones y procedimientos. Estos artefactos se clasifican en función del esquema al que pertenecen. Por lo tanto, otro uso de la vista basada en el artefacto es usar los artefactos que pertenecen a su esquema, así como los artefactos que pertenecen a otros esquemas. Esta vista también permite buscar artefactos en todos los esquemas.|  
|**Vista de esquema**|Esta vista está clasificada por los esquemas disponibles en la base de datos de Oracle subyacente. Use esta vista cuando sepa qué esquema tiene los artefactos que desea trabajar. En esta vista, los artefactos que se clasifica por categorías como API PL-SQL, procedimientos, funciones, tablas y vistas.|  
  
 Para obtener más información sobre cómo se clasifican los artefactos de Oracle E-Business Suite, consulte [conectarse a Oracle E-Business Suite en Visual Studio mediante el Asistente para agregar metadatos de adaptador](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md) otro motivo principal para organizar los artefactos de vistas diferentes es la facilidad para buscar artefactos específicos. Para obtener más información sobre cómo puede buscar artefactos, consulte [búsqueda para las operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md).  
  
> [!IMPORTANT]
>  Los nodos se muestran en función de la conexión que especifique al establecer una conexión de URI. Si especifica las credenciales que no tiene permisos en los artefactos de Oracle E-Business Suite, no puede usar los artefactos de la **vista basada en la aplicación**. Además, el **vista basada en el artefacto** no enumera los artefactos que pertenecen a Oracle E-Business Suite.  
  

  
## <a name="see-also"></a>Vea también  
 [Obtener metadatos para operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)