---
title: Winform软件开发技术基础
tags: Winform编程
categories:
  - 'C#-学习'
  - 金旭亮老师系列课程
date: 2019-02-21 18:13:42
---


{% centerquote %} 掌握桌面程序开发、熟悉常用的控件 {% endcenterquote %}
<!-- more -->

# 使用VisualStudio 编写GUI程序

本博客内容由金旭亮老师网上上传的文档制作，在此特地感谢！

## GUI应用程序简介

![1546164897285](Winform软件开发技术基础/1546164897285.png)

![1546164921162](Winform软件开发技术基础/1546164921162.png)

![1546164942820](Winform软件开发技术基础/1546164942820.png)

## 使用VisualStudio设计可视化桌面应用

![1546164971723](Winform软件开发技术基础/1546164971723.png)

![1546164997894](Winform软件开发技术基础/1546164997894.png)

![1546165032868](Winform软件开发技术基础/1546165032868.png)

![1546165059867](Winform软件开发技术基础/1546165059867.png)

![1546165082239](Winform软件开发技术基础/1546165082239.png)

![1546165102163](Winform软件开发技术基础/1546165102163.png)

![1546165122402](Winform软件开发技术基础/1546165122402.png)

![1546165139524](Winform软件开发技术基础/1546165139524.png)

## 快速应用开发模式

![1546165160484](Winform软件开发技术基础/1546165160484.png)

![1546165184564](Winform软件开发技术基础/1546165184564.png)

![1546165201365](Winform软件开发技术基础/1546165201365.png)

![1546165221425](Winform软件开发技术基础/1546165221425.png)

![1546165238072](Winform软件开发技术基础/1546165238072.png)

# 常用Winform控件使用

![1546165351543](Winform软件开发技术基础/1546165351543.png)

## 按钮控件

![1546165374922](Winform软件开发技术基础/1546165374922.png)

![1546165393399](Winform软件开发技术基础/1546165393399.png)

![1546165415675](Winform软件开发技术基础/1546165415675.png)

### 设计带图标的按钮

![1546165431522](Winform软件开发技术基础/1546165431522.png)

![1546165466587](Winform软件开发技术基础/1546165466587.png)

![1546165484437](Winform软件开发技术基础/1546165484437.png)

![1546165500856](Winform软件开发技术基础/1546165500856.png)

### 资源的使用

![1546165533575](Winform软件开发技术基础/1546165533575.png)

![1546165553059](Winform软件开发技术基础/1546165553059.png)

### 使用资源后需要注意的属性

![1546165572554](Winform软件开发技术基础/1546165572554.png)

![1546165589296](Winform软件开发技术基础/1546165589296.png)

## 标签控件

![1546165630891](Winform软件开发技术基础/1546165630891.png)

![1546165651949](Winform软件开发技术基础/1546165651949.png)

![1546165669015](Winform软件开发技术基础/1546165669015.png)

![1546165683764](Winform软件开发技术基础/1546165683764.png)

![1546165699570](Winform软件开发技术基础/1546165699570.png)

![1546165716234](Winform软件开发技术基础/1546165716234.png)

## 文本控件

![1546165735990](Winform软件开发技术基础/1546165735990.png)

![1546165767967](Winform软件开发技术基础/1546165767967.png)

![1546165783021](Winform软件开发技术基础/1546165783021.png)

![1546165798706](Winform软件开发技术基础/1546165798706.png)

![1546165814686](Winform软件开发技术基础/1546165814686.png)

![1546165833628](Winform软件开发技术基础/1546165833628.png)

![1546165850534](Winform软件开发技术基础/1546165850534.png)

![1546165863428](Winform软件开发技术基础/1546165863428.png)

![1546165887323](Winform软件开发技术基础/1546165887323.png)

![1546165904452](Winform软件开发技术基础/1546165904452.png)

![1546165923145](Winform软件开发技术基础/1546165923145.png)

## 进度条和小闹钟控件

![1546165944879](Winform软件开发技术基础/1546165944879.png)

![1546165962004](Winform软件开发技术基础/1546165962004.png)

![1546165983962](Winform软件开发技术基础/1546165983962.png)

```csharp
namespace ProgressBarAndTimer
{
    public partial class frmMain : Form
    {
        public frmMain()
        {
            InitializeComponent();
            ShowProgressBarValue(AutoProgressBar.Value);
        }

        private void ShowProgressBarValue(int value)
        {
            lblInfo.Text = string.Format("{0}%", value);
        }
        #region "事件响应"
        private void btnIncrease_Click(object sender, EventArgs e)
        {
            if (ManualProgressBar.Value + 2 > ManualProgressBar.Maximum)
            {
                ManualProgressBar.Value = ManualProgressBar.Maximum;
            }
            else
            {
                ManualProgressBar.Value += 2;
            }

        }

        private void btnDecrease_Click(object sender, EventArgs e)
        {
            if (ManualProgressBar.Value - 2 < ManualProgressBar.Minimum)
            {
                ManualProgressBar.Value = ManualProgressBar.Minimum;
            }
            else
            {
                ManualProgressBar.Value -= 2;
            }
        }

        private void timer1_Tick(object sender, EventArgs e)
        {
            if (AutoProgressBar.Value + 2 > AutoProgressBar.Maximum)
            {
                //自动回头
                AutoProgressBar.Value = 0;
            }
            else
            {
                AutoProgressBar.Value += 2;
            }
            ShowProgressBarValue(AutoProgressBar.Value);
        }

        private void btnTimer_Click(object sender, EventArgs e)
        {
            timer1.Enabled = !timer1.Enabled;
            if (timer1.Enabled == true)
            {
                btnTimer.Image = Resources.DisableClock;

            }
            else
            {
                btnTimer.Image = Resources.EnableClock;
            }
        }

        #endregion
    }
}
```

![1546165999161](Winform软件开发技术基础/1546165999161.png)

![1546166011637](Winform软件开发技术基础/1546166011637.png)

## 控件学习指导

![1546166036124](Winform软件开发技术基础/1546166036124.png)

![1546166051659](Winform软件开发技术基础/1546166051659.png)

![1546166066266](Winform软件开发技术基础/1546166066266.png)

![1546166085312](Winform软件开发技术基础/1546166085312.png)

# 使用容器控件布局窗体

## 学会学习

![1546166159650](Winform软件开发技术基础/1546166159650.png)

![1546166176467](Winform软件开发技术基础/1546166176467.png)

![1546166191931](Winform软件开发技术基础/1546166191931.png)

## 控件Anchor属性

![1546166207278](Winform软件开发技术基础/1546166207278.png)

## 控件Dock属性

![1546166219153](Winform软件开发技术基础/1546166219153.png)

```csharp
namespace FormCtrlProperty
{
    public partial class frmDock : Form
    {
        public frmDock()
        {
            InitializeComponent();
        }

        private void rdoNone_CheckedChanged(object sender, EventArgs e)
        {
            button1.Dock = DockStyle.None;
        }

        private void rdoLeft_CheckedChanged(object sender, EventArgs e)
        {
            button1.Dock = DockStyle.Left;
        }

        private void rdoRight_CheckedChanged(object sender, EventArgs e)
        {
            button1.Dock = DockStyle.Right;
        }

        private void rdoTop_CheckedChanged(object sender, EventArgs e)
        {
            button1.Dock = DockStyle.Top;
        }

        private void rdoBottom_CheckedChanged(object sender, EventArgs e)
        {
            button1.Dock = DockStyle.Bottom;
        }

        private void rdoFill_CheckedChanged(object sender, EventArgs e)
        {
            button1.Dock = DockStyle.Fill;
        }
    }
}

```

## 容器控件

![1546166272072](Winform软件开发技术基础/1546166272072.png)

### 面板Panel

![1546166287071](Winform软件开发技术基础/1546166287071.png)

```csharp
namespace ContainerDemo
{
    public partial class frmPanel : Form
    {
        public frmPanel()
        {
            InitializeComponent();
        }

        private void btnShowOrHide_Click(object sender, EventArgs e)
        {
            if (rdoOuter.Checked)
            {
                pnlOuter.Visible = !pnlOuter.Visible;

            }
            else
            {
                pnlInner.Visible = !pnlInner.Visible;
            }
            ChangebtnShowOrHideText();
        }

        private void btnEnableOrDisable_Click(object sender, EventArgs e)
        {
            if (rdoOuter.Checked)
            {
                pnlOuter.Enabled = !pnlOuter.Enabled;
            }
            else
            {
                pnlInner.Enabled = !pnlInner.Enabled;
            }
            ChangebtnEnableOrDisableText();
        }

        private void ChangebtnShowOrHideText()
        {
            if (rdoOuter.Checked)
            {
                btnShowOrHide.Text = pnlOuter.Visible ? "隐藏" : "显示";

            }
            else
            {
                btnShowOrHide.Text = pnlInner.Visible ? "隐藏" : "显示";
            }
        }
        private void ChangebtnEnableOrDisableText()
        {
            if (rdoOuter.Checked)
            {
                btnEnableOrDisable.Text = pnlOuter.Enabled ? "禁用" : "激活";

            }
            else
            {
                btnEnableOrDisable.Text = pnlInner.Enabled ? "禁用" : "激活";
            }
        }

        private void rdoOuter_CheckedChanged(object sender, EventArgs e)
        {
            ChangebtnEnableOrDisableText();
            ChangebtnShowOrHideText();
        }

        private void rdoInner_CheckedChanged(object sender, EventArgs e)
        {
            ChangebtnEnableOrDisableText();
            ChangebtnShowOrHideText();
        }
    }
}
```

### 组合框GropBox

![1546166301687](Winform软件开发技术基础/1546166301687.png)

### 选项卡TabControl

![1546166318969](Winform软件开发技术基础/1546166318969.png)

![1546166334015](Winform软件开发技术基础/1546166334015.png)

```csharp
namespace ContainerDemo
{
    public partial class frmTabControl : Form
    {
        public frmTabControl()
        {
            InitializeComponent();
            tabCount = tabControl1.TabPages.Count;
        }

        private int tabCount = 0;
        private Random ran = new Random();
        private void btnAddTab_Click(object sender, EventArgs e)
        {
            tabCount++;
            TabPage newPage = new TabPage("tabPage" + tabCount);
            newPage.BackColor = Color.FromArgb(
                ran.Next(0,255),
                ran.Next(0,255),
                ran.Next(0,255));
            tabControl1.TabPages.Add(newPage);

        }

        private void btnActiveLeft_Click(object sender, EventArgs e)
        {
            if (tabControl1.SelectedIndex != 0)
            {
                tabControl1.SelectTab(tabControl1.SelectedIndex - 1);
            }
        }

        private void btnActiveRight_Click(object sender, EventArgs e)
        {
            if (tabControl1.SelectedIndex != tabControl1.TabPages.Count - 1)
            {
                tabControl1.SelectTab(tabControl1.SelectedIndex + 1);
            }
        }
    }
}
```

![1546166346105](Winform软件开发技术基础/1546166346105.png)

# 使用容器控件布局窗体

## 分割条面板SplitContainer

![1546166416490](Winform软件开发技术基础/1546166416490.png)

![1546166428181](Winform软件开发技术基础/1546166428181.png)

## FlowLayout控件

![1546166442299](Winform软件开发技术基础/1546166442299.png)

```csharp
namespace LayoutDemos
{
    public partial class frmFlowLayout : Form
    {
        public frmFlowLayout()
        {
            InitializeComponent();
        }

        private int counter = 0;
        private void btnAddButton_Click(object sender, EventArgs e)
        {
            counter++;
            Button btn = new Button();
            btn.Text = "按钮" + counter;
            flowLayoutPanel1.Controls.Add(btn);

        }

        private void chkWrapContents_CheckedChanged(object sender, EventArgs e)
        {

                flowLayoutPanel1.WrapContents = chkWrapContents.Checked;

        }

        private void chkAutoScroll_CheckedChanged(object sender, EventArgs e)
        {
            flowLayoutPanel1.AutoScroll = chkAutoScroll.Checked;
        }

        private void cboFlowDirection_SelectedIndexChanged(object sender, EventArgs e)
        {
            switch (cboFlowDirection.Text)
            {
                case "BottomUp":
                    flowLayoutPanel1.FlowDirection = FlowDirection.BottomUp;
                    break;
                case "LeftToRight":
                    flowLayoutPanel1.FlowDirection = FlowDirection.LeftToRight;
                    break;
                case "RightToLeft":
                    flowLayoutPanel1.FlowDirection = FlowDirection.RightToLeft;
                    break;
                case "TopDown":
                    flowLayoutPanel1.FlowDirection = FlowDirection.TopDown;
                    break;
                default:
                    break;
            }
        }
    }
}

```

## TabelLayoutPanel

![1546166454038](Winform软件开发技术基础/1546166454038.png)

![1546166470129](Winform软件开发技术基础/1546166470129.png)

![1546166485412](Winform软件开发技术基础/1546166485412.png)

![1546166498949](Winform软件开发技术基础/1546166498949.png)

# 复杂一些的控件

## 对话框

![1546164188573](Winform软件开发技术基础/1546164188573.png)

![1546164209289](Winform软件开发技术基础/1546164209289.png)

```csharp
namespace DialogDemo
{
    public partial class frmMain : Form
    {
        public frmMain()
        {
            InitializeComponent();
        }

        private void btnOpenFile_Click(object sender, EventArgs e)
        {
            openFileDialog1.Title = "选择一张图片";
            openFileDialog1.Filter = "所有支持的图片文件|*.jpg;*.gif;*.png;*.bmp|任意文件（*.*）|*.*";
            openFileDialog1.FileName = "";
            openFileDialog1.InitialDirectory = Environment.GetFolderPath(Environment.SpecialFolder.MyPictures);
            openFileDialog1.CheckFileExists = true;
            openFileDialog1.CheckPathExists = true;

			//是否允许选择多个文件
            //openFileDialog1.Multiselect = false;
            openFileDialog1.Multiselect = true;
            if (openFileDialog1.ShowDialog() == DialogResult.OK)
            {
                if (openFileDialog1.Multiselect == false)
                {
                    lblInfo.Text = openFileDialog1.FileName;
                }
                else
                {
                    StringBuilder sb = new StringBuilder();
                    foreach (var file in openFileDialog1.FileNames)
                    {
                        sb.Append(file);
                        sb.Append("\n");
                    }
                    lblInfo.Text = sb.ToString();
                }
            }

        }

        private void btnSaveFile_Click(object sender, EventArgs e)
        {
        	//设置默认文件扩展名
            saveFileDialog1.DefaultExt = ".txt";
            //指定文件名存在，是否提示警告
            saveFileDialog1.OverwritePrompt = true;
            saveFileDialog1.Title = "保存文件";
            if (saveFileDialog1.ShowDialog() == DialogResult.OK)
            {
                lblInfo.Text = "文件己保存到：" + saveFileDialog1.FileName;
            }
        }

        private void btnFontDialog_Click(object sender, EventArgs e)
        {
            if (fontDialog1.ShowDialog() == DialogResult.OK)
            {
                lblInfo.Font = fontDialog1.Font;
            }
        }

        private void btnColor_Click(object sender, EventArgs e)
        {
            if (colorDialog1.ShowDialog() == DialogResult.OK)
            {
                lblInfo.ForeColor = colorDialog1.Color;
            }
        }
    }
}
```

![1546164225092](Winform软件开发技术基础/1546164225092.png)

## 下拉菜单

![1546164272884](Winform软件开发技术基础/1546164272884.png)

弹出式菜单：例如鼠标点右键

![1546164297420](Winform软件开发技术基础/1546164297420.png)

![1546164371528](Winform软件开发技术基础/1546164371528.png)

![1546164387791](Winform软件开发技术基础/1546164387791.png)

![1546410893351](Winform软件开发技术基础/1546410893351.png)

## 弹出式菜单

![1546164455595](Winform软件开发技术基础/1546164455595.png)

![1546164471327](Winform软件开发技术基础/1546164471327.png)

```csharp
namespace MenuDemo
{
    public partial class frmMain : Form
    {
        public frmMain()
        {
            InitializeComponent();
        }

        private void mnuExit_Click(object sender, EventArgs e)
        {
            Close();
        }

        private void menuOpen_Click(object sender, EventArgs e)
        {
            openFileDialog1.ShowDialog();
        }

        private void btnEnable_Click(object sender, EventArgs e)
        {
            FileMenuItem.Enabled = !FileMenuItem.Enabled;
        }

        private int SaveCount = 0;
        private void mnuSave_Click(object sender, EventArgs e)
        {
            SaveCount++;
            mnuSave.Text = string.Format("保存({0})", SaveCount);
        }

        private void btnExchange_Click(object sender, EventArgs e)
        {
            menuStripEdit.Visible = !menuStripEdit.Visible;
            menuStripFile.Visible = !menuStripFile.Visible;
        }

        private void buttonShowContextMenu_Click(object sender, EventArgs e)
        {
       									 //相对于指定控件定位
            contextMenuStripExample.Show(sender as Control,20,25);
        }
    }
}
```

## 状态条

![1546164493810](Winform软件开发技术基础/1546164493810.png)

![1546164523376](Winform软件开发技术基础/1546164523376.png)

```csharp
namespace StatusStripDemo
{
    public partial class frmStatusStrip : Form
    {
        public frmStatusStrip()
        {
            InitializeComponent();
        }

        private void btnShowTime_Click(object sender, EventArgs e)
        {
            timerForCurrentTime.Enabled = !timerForCurrentTime.Enabled;
        }

        private void timer1_Tick(object sender, EventArgs e)
        {
            toolStripStatusLabel1.Text = DateTime.Now.ToLongTimeString();
        }

        private void ToolStripMenuItem1_Click(object sender, EventArgs e)
        {
            MessageBox.Show("菜单项一");
        }

        private void ToolStripMenuItem2_Click(object sender, EventArgs e)
        {
            MessageBox.Show("菜单项二");
        }

        private void ToolStripMenuItem3_Click(object sender, EventArgs e)
        {
            MessageBox.Show("菜单项三");
        }

        private void btnShowProgress_Click(object sender, EventArgs e)
        {
            toolStripProgressBar1.Visible = true;
            toolStripProgressBar1.Value = 0;
            timerForProgress.Enabled = true;
            btnShowProgressBar.Enabled = false;
        }

        private void timerForProgress_Tick(object sender, EventArgs e)
        {
            if (toolStripProgressBar1.Value < 100)
                toolStripProgressBar1.Value += 5;
            else
            {
                toolStripProgressBar1.Visible = false;
                timerForProgress.Enabled = false;
                btnShowProgressBar.Enabled = true;
            }

        }
    }
}
```

![1546164705543](Winform软件开发技术基础/1546164705543.png)

![1546164727897](Winform软件开发技术基础/1546164727897.png)

## 树

![1546164751440](Winform软件开发技术基础/1546164751440.png)

![1546164780836](Winform软件开发技术基础/1546164780836.png)

![1546164800934](Winform软件开发技术基础/1546164800934.png)

![1546164835672](Winform软件开发技术基础/1546164835672.png)

```csharp
namespace TreeDemo
{
    public partial class frmMain : Form
    {
        public frmMain()
        {
            InitializeComponent();
        }

        private void btnNewTopNode_Click(object sender, EventArgs e)
        {
            string NodeText = "";
            if (!string.IsNullOrEmpty(txtNewNodeText.Text.Trim()))
            {
                NodeText = txtNewNodeText.Text;
            }
            else
            {
                NodeText = "新根节点" + (treeView1.GetNodeCount(true) + 1);

            }

            treeView1.Nodes.Add(NodeText);
        }

        private void btnAddBrotherNode_Click(object sender, EventArgs e)
        {
            string NodeText = "";
            if (treeView1.SelectedNode != null && treeView1.SelectedNode.Parent!=null)
            {
                if (!string.IsNullOrEmpty(txtNewNodeText.Text.Trim()))
                {
                    NodeText = txtNewNodeText.Text;
                }
                else
                {
                    NodeText = "新兄弟节点" + (treeView1.GetNodeCount(true) + 1);
                }
                treeView1.SelectedNode.Parent.Nodes.Add(NodeText);
            }
        }

        private void btnAddChildNode_Click(object sender, EventArgs e)
        {
            string NodeText = "";
            if (treeView1.SelectedNode != null)
            {
                if (!string.IsNullOrEmpty(txtNewNodeText.Text.Trim()))
                {
                    NodeText = txtNewNodeText.Text;
                }
                else
                {
                    NodeText = "新子节点" + (treeView1.GetNodeCount(true) + 1);
                }
                treeView1.SelectedNode.Nodes.Add(NodeText);
                treeView1.SelectedNode.Expand();
            }
        }

        private void btnDeleteNode_Click(object sender, EventArgs e)
        {
            if (treeView1.SelectedNode != null)
            {
                if (treeView1.SelectedNode.Parent != null)
                {
                    treeView1.SelectedNode.Parent.Nodes.Remove(treeView1.SelectedNode);
                }
                else
                {
                    treeView1.Nodes.Remove(treeView1.SelectedNode);
                }
            }
        }

        private void btnClearTreeNodes_Click(object sender, EventArgs e)
        {
            treeView1.Nodes.Clear();
        }

        private void btnExpandCollapseNode_Click(object sender, EventArgs e)
        {
            if (treeView1.SelectedNode != null)
            {
                if (treeView1.SelectedNode.IsExpanded)
                {
                    treeView1.SelectedNode.Collapse(true);
                }
                else
                {
                    treeView1.SelectedNode.Expand();
                }
            }
        }

        private void treeView1_AfterSelect(object sender, TreeViewEventArgs e)
        {
            txtNodeText.Text = e.Node.Text;
        }

        private void btnNodeRename_Click(object sender, EventArgs e)
        {
            if (txtNodeText.Text.Trim().Length > 0)
            {
                treeView1.SelectedNode.Text = txtNodeText.Text.Trim();
            }
        }
    }
}
```
