# Metodo para refrescar el DataSource de un formulario Caller
public class ItemGridLinesTmp_AT extends FormRun
{
    EcoResProductMaster productMasterCaller;
    DimComboType_AT     dimComboType;


  public void init()
  {
    ItemGridLinesTmp_AT tmpTable;
    ItemGridLines_AT itemGridLines_AT;

    super();

    if (element.args().caller())
    {
        callerFormRun = element.args().caller() as FormRun;
    }



    if (element.args().caller())
{

    if (callerFormRun)
    {
        #Task
        callerFormRun.task(#taskRefresh);
    }
}

element.close();
