# Drivers-para-jasper-report















Codigo:
import net.sf.jasperreports.engine.JRException;
import net.sf.jasperreports.engine.JasperFillManager;
import net.sf.jasperreports.engine.JasperPrint;
import net.sf.jasperreports.engine.JasperReport;
import net.sf.jasperreports.engine.util.JRLoader;
import net.sf.jasperreports.view.JasperViewer;

 JasperReport reporte = null;
            String path ="src"+File.separator+File.separator+"report.jasper";
            
            // para que pueda cargar el archivo .jasper
            reporte = (JasperReport) JRLoader.loadObjectFromFile(path);
            
            // llenado del reporte
            JasperPrint jprint = JasperFillManager.fillReport(reporte,null,conexion);
            
            
            // vista del reporte
            JasperViewer view = new JasperViewer(jprint, false);
            view.setTitle("Reorte de escuelas");
            // Para que pueda cerrar este reporte
            view.setDefaultCloseOperation(DISPOSE_ON_CLOSE);
            
            // hacer visible el reporte
           
            view.setVisible(true);
        } catch (JRException ex) {
            Logger.getLogger(TablaDeEscuelas.class.getName()).log(Level.SEVERE, null, ex);
        }
