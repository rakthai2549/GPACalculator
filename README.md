# GPACalculator
using System;
using System.Windows.Forms;

namespace WinFormsApp1
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            try
            {
                double maxGrade = double.Parse(txtMaxGrade.Text);
                double minGrade = double.Parse(txtMinGrade.Text);
                int peopleCount = int.Parse(txtCount.Text);

                if (peopleCount <= 0)
                {
                    MessageBox.Show("จำนวนคนต้องมากกว่า 0", "ข้อผิดพลาด", MessageBoxButtons.OK, MessageBoxIcon.Error);
                    return;
                }

                double gpaX = (maxGrade + minGrade) / 2;
                double maxScore = maxGrade * 25; // สมมติว่า 4.0 = 100 คะแนน
                double minScore = minGrade * 25;

                txtGPAx.Text = gpaX.ToString("F2");
                txtMaxScore.Text = maxScore.ToString("F2");
                txtMinScore.Text = minScore.ToString("F2");
            }
            catch (Exception ex)
            {
                MessageBox.Show("กรุณากรอกข้อมูลให้ถูกต้อง\n" + ex.Message, "ข้อผิดพลาด", MessageBoxButtons.OK, MessageBoxIcon.Error);
            }
        }
    }
}
