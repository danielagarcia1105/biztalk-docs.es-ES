---
title: "Asistente para la configuración de línea de comandos para el adaptador de MQSeries | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [MQSeries adapters], silent configuration
- MQSeries adapters, silent configuration
- configuring [MQSeries adapters], Command-Line Configuration Wizard
- Command-Line Configuration Wizard
- MQSeries adapters, Command-Line Configuration Wizard
ms.assetid: cab905d1-fe19-4d6a-be1b-f561e133e1d2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee73b890fca43a3651f22092486e5898862b0b72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="command-line-configuration-wizard-for-the-mqseries-adapter"></a>Asistente para la configuración de línea de comandos para el adaptador de MQSeries
El asistente dispone de cuatro opciones para instalar, desinstalar y registrar acciones.  
  
## <a name="syntax"></a>Sintaxis  
 **mqsconfigwiz [/ u] [/i config.xml] [/l logfile] [¿/?]**  
  
|Opción|Description|  
|------------|-----------------|  
|**/u**|Desinstala MQSAgent.|  
|**/i** *config.xml*|Instala MQSAgent utilizando la información en el archivo *config.xml*.|  
|**/l** *archivo de registro*|Registra acciones en el archivo *archivo de registro*.|  
|**/?**|Muestra un cuadro de diálogo que describe las opciones de línea de comandos.|  
  
 El contenido del archivo XML que guarda la información de configuración puede variar en función de la versión de Windows que se esté utilizando. Para obtener más información acerca del formato de archivo de configuración, consulte [archivo de configuración XML para el adaptador de MQSeries](../core/xml-configuration-file-for-the-mqseries-adapter.md).  
  
> [!IMPORTANT]
>  El adaptador no funciona mientras se está ejecutando el Asistente para configuración.  
  
> [!NOTE]
>  No podrá volver a configurar MQSAgent con el Asistente para configuración de línea de comandos. En primer lugar debe ejecutar el Asistente para desinstalar el agente (**/u**), y, a continuación, ejecútelo para configurar (**/i**).  
  
## <a name="see-also"></a>Vea también  
 [Configuración silenciosa del adaptador de MQSeries](../core/silent-configuration-of-the-mqseries-adapter.md)