using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Web.UI;
using System.Web.UI.WebControls;
using System.Data.SqlClient;

public partial class _Default : System.Web.UI.Page
{
    TextBox txtbx1;
    TextBox txtbx2;
    Table tbl;
    TableCell cell;
    int i;
    int txt1;

    //string wizPage;
    //string strCustID;
    //int intCustID;

    //SqlConnection conn;

    protected void Page_Load(object sender, EventArgs e)
        {
            // Gets CustID from Querysting
            // Then converts to int
            //strCustID = Request.QueryString[0];
            //intCustID = Convert.ToInt32(strCustID);
            if (Page.IsPostBack)
            {
                txt1 = Convert.ToInt16(numBox.Text);
                tbl = new Table();

                tbl.ID = "table1";



                for (i = 0; i < txt1; i++)
                {

                    txtbx1 = new TextBox();
                    txtbx2 = new TextBox();
                    txtbx1.ID = "Name" + i;
                    txtbx2.ID = "Des" + i;
                    txtbx1.Width = 300;
                    txtbx2.Width = 300;
                    txtbx2.Height = 200;
                    txtbx2.TextMode = TextBoxMode.MultiLine;
                    txtbx2.Wrap = true;
                    txtbx1.MaxLength = 50;
                    txtbx2.MaxLength = 1000;
                    TableRow rw = new TableRow();
                    TableRow rw2 = new TableRow();
                    cell = new TableCell();
                    TableCell cell2 = new TableCell();



                    cell.Controls.Add(txtbx1);
                    cell.Controls.Add(txtbx2);
                    rw.Cells.Add(cell);
                    rw2.Cells.Add(cell2);
                    tbl.Controls.Add(rw);
                    tbl.Controls.Add(rw2);
                    pnlButton1.Controls.Add(tbl);
                    //pnlButton2.Controls.Add(tbl2);
                    Literal lit = new Literal();
                    lit.Text = "</br></br>";
                    Literal lit2 = new Literal();
                    lit2.Text = "</br></br>";
                    pnlButton2.Controls.Add(lit2);
                    pnlButton1.Controls.Add(lit);
                }
            }
        }

        protected void addBox_Click(object sender, EventArgs e)
        {
            /*double txt1 = Convert.ToDouble(numBox.Text);
            Table tbl = new Table();

            tbl.ID = "table1";



            for (int i = 0; i < txt1; i++)
            {

                txtbx1 = new TextBox();
                txtbx2 = new TextBox();
                txtbx1.ID = "Name" + i;
                txtbx2.ID = "Des" + i;                
                txtbx1.Width = 300;
                txtbx2.Width = 300;
                txtbx2.Height = 200;
                txtbx2.TextMode = TextBoxMode.MultiLine;
                txtbx2.Wrap = true;
                txtbx1.MaxLength = 50;
                txtbx2.MaxLength = 1000;
                TableRow rw = new TableRow();
                TableRow rw2 = new TableRow();
                TableCell cell = new TableCell();
                TableCell cell2 = new TableCell();



                cell.Controls.Add(txtbx1);
                cell.Controls.Add(txtbx2);
                rw.Cells.Add(cell);
                rw2.Cells.Add(cell2);
                tbl.Controls.Add(rw);
                tbl.Controls.Add(rw2);
                pnlButton1.Controls.Add(tbl);
                //pnlButton2.Controls.Add(tbl2);
                Literal lit = new Literal();
                lit.Text = "</br></br>";
                Literal lit2 = new Literal();
                lit2.Text = "</br></br>";
                pnlButton2.Controls.Add(lit2);
                pnlButton1.Controls.Add(lit);
            }*/
        }

        protected void submitForm_Click(object sender, EventArgs e)
        {
           /* // Create DB connection
            using (conn = new SqlConnection(CongifManage.ConnectionStrings["conn"].ConnectionString))
                
            {
                //open conn
                conn.Open();

                //Declare Variables

                
               
                for (i = 0; i < txt1; i++ )
                {
                    TextBox nameBox = (TextBox)cell.FindControl(("Name" + i));
                    TextBox desBox = (TextBox)cell.FindControl(("Des" + i));
                    string ProgName = nameBox.Text;
                    string ProgDes = desBox.Text;

                    try
                    {
                        //conn.Open();

                        using (SqlCommand cmdAddSafe = conn.CreateCommand())
                        {
                            cmdAddSafe.CommandText = CongifManage.AppSettings["addSafe"];

                            cmdAddSafe.Parameters.AddWithValue("@CustID", intCustID);
                            cmdAddSafe.Parameters.AddWithValue("@ProgName", ProgName);
                            cmdAddSafe.Parameters.AddWithValue("@ProgDes", ProgDes);

                            cmdAddSafe.ExecuteNonQuery();
                        }
                    }
                    catch (SqlException exception)
                    {
                        ErrMsg.Text = "Error No: " + exception.Number + " | Error Message: " + exception.Message;
                        return;
                    }

                }
                //close conn
                conn.Close();

                // Redirect to ClearyInfo Page
                // Append CustID to page
                wizPage = "Wizard.aspx?custID=" + intCustID;
                Response.Redirect(wizPage);
            }*/
        }
    }
