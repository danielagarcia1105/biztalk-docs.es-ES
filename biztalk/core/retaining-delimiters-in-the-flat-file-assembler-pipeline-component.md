---
title: Conservar delimitadores en el componente de canalización de ensamblador de archivo sin formato | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: adc27561-9996-49a9-b715-e313b9148506
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9d10879adfbe0ca0c68376faa48d9976fc19599
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268788"
---
# <a name="retaining-delimiters-in-the-flat-file-assembler-pipeline-component"></a>Conservar delimitadores en el componente de canalización de ensamblador de archivos sin formato
Si faltan registros en el mensaje que va a pasar a través de una canalización personalizada que usa el ensamblador de archivo sin formato, el delimitador para dichos registros puede aparecer o no en la salida de archivo sin formato según la ubicación del archivo de entrada en la que faltan los registros.  
  
 Para garantizar que el archivo sin formato conserve determinados delimitadores, puede usar una asignación y una secuencia de comandos personalizada para asegurarse de que se ha creado un registro "vacío" cuando no existe un registro de entrada específico en el mensaje. Para que funcione, debe comprobar que los nodos potencialmente vacíos del esquema de documento del ensamblador de archivo sin formato tengan las propiedades siguientes configuradas como se indica a continuación:  
  
|Propiedad|Configuración|  
|--------------|-------------|  
|Conservar delimitador para datos vacíos|Sí|  
|Suprimir delimitadores finales|No|  
|Generar nodos vacíos (configurar en el nodo raíz)|True|  
  
### <a name="to-create-a-map-that-creates-an-empty-record"></a>Para crear una asignación que crea un registro "vacío"  
  
1.  Agregue una nueva asignación al proyecto de BizTalk.  
  
2.  Especifique el esquema de documento usado por el ensamblador de archivo sin formato como esquema de origen y de destino de la asignación.  
  
3.  Asigne los campos de origen que no estarán vacíos en los correspondientes campos de destino.  
  
4.  Para los archivos que pueden estar vacíos, use una secuencia de comandos personalizada para comprobar si el campo de origen está vacío y devuelve una cadena vacía (en lugar de Nulo). Use una secuencia de comandos como la siguiente:  
  
    ```  
    public string ValOrEmpty(string val)  
    {  
         return (val.Length > 0) ? val : "";  
    }  
    ```  
  
    > [!NOTE]
    >  Debe crear una secuencia de comandos con un nombre de función único para cada campo potencialmente vacío que asigne. Por ejemplo, si tiene tres campos que pueden estar vacíos, podría tener funciones denominadas `ValOrEmpty1`, `ValOrEmpty2`, `ValOrEmpty3`.  
  
5.  Con la Consola de administración de BizTalk Server, configure el puerto de envío con la canalización personalizada y el componente de ensamblador de archivo sin formato para usar la asignación como asignación saliente.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar asignaciones de salida para un puerto de envío](../core/how-to-configure-outbound-maps-for-a-send-port.md)   
 [Componente de canalización de ensamblador de archivo sin formato](../core/flat-file-assembler-pipeline-component.md)