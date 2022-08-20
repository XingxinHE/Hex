- # 😎Quick Digest -> Qt
	- ## 📝Definition
	  Qt is a well-known cross-platform C++ application framework which provides developers with the functionality they need to build a Graphics User Interface (GUI).
	- ## 🏷(Sub)Categories
	  What are the sub objects of this subject?
		- The architecture of Qt
			- Qt SDK：包含了 Qt 库以及 Qt 的开发工具，是一套完整的开发环境。
			- Qt Creator：基于 Qt 构建的一个轻量级 IDE，支持语法高亮、代码补全等功能，是一款轻便实用的 IDE。
			- Qt Designer：一个功能强大的 GUI 布局与窗体构造器，能够在所有支持的平台上，以本地化的试图外观与认知，快速开发高性能的用户界面。
	- ## 🧪Composition
	  What kind of stuffs composite this subject?
		- Qt's Core Feature
			- The Meta-Object System
			- The Property System
			- Object Model
			- Object Trees & Ownership
			- Signals & Slots
				- The "signal" refers to the communication between application and user interaction.
				- For example, once an "event" is touched, a button was clicked and it will make a "signal". The "signal" itself is aimless while if someone is interested in this guy... It must use the function `connect` which is called a slot function to process this signal.
				- This feature is one of the dominant feature of Qt.
	- ## 🎯Intent
	   A short description what does this thing do?
	- ## 🧠Intuition
	  Find an intuitive way of explanation of this concept.
	- ## 🚀Benefit
	   A scenario that illustrates the benefit this object provides.
	- ## ⌨Sample Code
	   Code fragments
		- ### Qt Hello World
		  collapsed:: true
			- Qt Creator - File - New Project - Application(Qt) - Qt Widget Application - All the Way Down...
			- The Qt Creator helps you creating following files by default.
				- `main.cpp`
					- ``` c++
					  #include "mainwindow.h"
					  
					  #include <QApplication>
					  
					  int main(int argc, char *argv[])
					  {
					      QApplication a(argc, argv);		//👈create a Qt application
					      MainWindow w;					//👈create the main window
					      w.show();						//👈display the main window
					      return a.exec();				//👈delegate this app to Qt
					  }
					  
					  ```
				- `mainwindow.h`
					- ``` c++
					  #ifndef MAINWINDOW_H
					  #define MAINWINDOW_H
					  
					  #include <QMainWindow>
					  
					  QT_BEGIN_NAMESPACE
					  namespace Ui { class MainWindow; }
					  QT_END_NAMESPACE
					  
					  class MainWindow : public QMainWindow
					  {
					      Q_OBJECT
					  
					  public:
					      MainWindow(QWidget *parent = nullptr);
					      ~MainWindow();
					  
					  private:
					      Ui::MainWindow *ui;		//👈defined by Qt .ui files
					  };
					  #endif // MAINWINDOW_H
					  
					  ```
				- `mainwindow.cpp`
					- ``` c++
					  #include "mainwindow.h"
					  #include "./ui_mainwindow.h"
					  
					  MainWindow::MainWindow(QWidget *parent)
					      : QMainWindow(parent)
					      , ui(new Ui::MainWindow)
					  {
					      ui->setupUi(this);  //👈UI initialization, the first most function to be invoked
					  }
					  
					  MainWindow::~MainWindow()
					  {
					      delete ui;
					  }
					  ```
			- Next we want to decorate this application.
				- Few stuffs to be included.
					- `QAction` - the action to the menu
					- `QMenu` - the menu
					- `QToolBar` - the tool bar
					- Normally we will
				- `main.cpp`
					- Nothing changed here.
				- `mainwindow.h`
					- ``` c++
					  #ifndef MAINWINDOW_H
					  #define MAINWINDOW_H
					  
					  #include <QMainWindow>
					  
					  QT_BEGIN_NAMESPACE
					  namespace Ui { class MainWindow; }
					  QT_END_NAMESPACE
					  
					  class MainWindow : public QMainWindow
					  {
					      Q_OBJECT
					  
					  public:
					      MainWindow(QWidget *parent = nullptr);
					      ~MainWindow();
					  
					  private:
					      Ui::MainWindow *ui;
					      QAction* mp_action; 		// 👈declare the action pointer
					      QMenu* mp_menu; 			// 👈declare the menu pointer
					      QToolBar* mp_toolbar;    // 👈declare the toolbar pointer
					  
					      void createButton();    // 👈declare function to create the ui button
					  
					  private slots:
					      void HelloWorld();      // 👈declare slot function
					  };
					  #endif // MAINWINDOW_H
					  
					  ```
				- `mainwindow.cpp`
					- ``` c++
					  #include "mainwindow.h"
					  #include "./ui_mainwindow.h"
					  #include <QToolBar>
					  #include <QMessageBox>
					  
					  MainWindow::MainWindow(QWidget *parent)
					      : QMainWindow(parent)
					      , ui(new Ui::MainWindow)
					  {
					      ui->setupUi(this);
					      createButton();
					  }
					  
					  MainWindow::~MainWindow()
					  {
					      delete ui;
					  }
					  
					  void MainWindow::createButton()
					  {
					      // 👇create action which labeled with "Hello world"
					      // the & here is to set the shortcut for the label, e.g. 'H'
					      mp_action = new QAction(tr("&Hello world"), this);
					  
					      // 👇connect the signal and the slot
					      // connect(signal sender, type of signal, signal receiver, slot function)
					      connect(mp_action, &QAction::triggered, this, &MainWindow::HelloWorld);
					  
					      // 👇create menu with label "Menu"
					      mp_menu = menuBar()->addMenu(tr("&Menu"));
					      // put action to the menu
					      mp_menu->addAction(m_action);
					  
					      // 👇create tool bar with label "Tool Bar"
					      mp_toolbar = addToolBar(tr("&Tool Bar"));
					      // add action to the tool bar
					      mp_toolbar->addAction(m_action);
					  }
					  
					  void MainWindow::HelloWorld()
					  {
					      // 👇the slot function mererly pops up a message box
					      QMessageBox::about(this, tr("Hello world"),
					          tr("Well done! Go ahead."));
					  }
					  
					  ```
		- ### Qt Mini Draw
			- Detail codes can refer to
			- Setup
				- Qt Creator - File - New Project - Application(Qt) - Qt Widget Application
					- A project called "MiniDraw" based on `QMainWindow`
					- A project called "ViewWidget" based on `QWidget`
				- For files `viewwidget.cpp`，`viewwidget.h`，`viewwidget.ui` in "ViewWidget" project
					- move to "MiniDraw" project.
					- In `CMakeLists.txt` of "MiniDraw", included preceding files
			- First Version
				- `viewwidget.h`
				  collapsed:: true
					- ``` c++
					  #ifndef VIEWWIDGET_H
					  #define VIEWWIDGET_H
					  
					  #include <QWidget>
					  
					  QT_BEGIN_NAMESPACE
					  namespace Ui { class ViewWidget; }
					  QT_END_NAMESPACE
					  
					  class ViewWidget : public QWidget
					  {
					      Q_OBJECT
					  
					  public:
					      ViewWidget(QWidget *parent = nullptr);
					      ~ViewWidget();
					  
					  	/* Override the mouse event related functions */
					      void mousePressEvent(QMouseEvent *) override;
					      void mouseMoveEvent(QMouseEvent *) override;
					      void mouseReleaseEvent(QMouseEvent *) override;
					      void paintEvent(QPaintEvent *) override;
					  
					  	/* get-set functions of data members */
					      bool getDrawStatus() const {return m_drawStatus;}
					      void setDrawStatus(bool status) {m_drawStatus= status;}
					  
					      QPoint getStartPoint() const {return m_startPoint;}
					      void setStartPoint(QPoint pt) {m_startPoint = pt;}
					  
					      QPoint getEndPoint() const {return m_endPoint;}
					      void setEndPoint(QPoint pt) {m_endPoint = pt;}
					  
					  private:
					      Ui::ViewWidget *ui;
					  
					      bool m_drawStatus;
					      QPoint m_startPoint;
					      QPoint m_endPoint;
					  };
					  #endif // VIEWWIDGET_H
					  
					  ```
				- `viewwidget.cpp`
					- ``` c++
					  void ViewWidget::mouseMoveEvent(QMouseEvent *event)
					  {
					      if (getDrawStatus())
					      {
					          setEndPoint(event->pos());
					      }
					  }
					  
					  void ViewWidget::mousePressEvent(QMouseEvent *event)
					  {
					      if (Qt::LeftButton == event->button())
					      {
					          setDrawStatus(true);
					          setStartPoint(event->pos());
					          setEndPoint(event->pos());
					      }
					  }
					  
					  void ViewWidget::mouseReleaseEvent(QMouseEvent *event)
					  {
					      setDrawStatus(false);
					  }
					  
					  /*Function actually did the paint job*/
					  void ViewWidget::paintEvent(QPaintEvent *event)
					  {
					      QPainter painter(this);  //👈 define what painting of widget will be pointed to
					      painter.drawLine(getStartPoint(), getEndPoint());  //👈actually draw using painter
					      painter.end();
					      update();
					  }
					  ```
				- `minidraw.h`
					- The codes are more or less the same as the Qt Hello World.
					  ``` c++
					  #ifndef MINIDRAW_H
					  #define MINIDRAW_H
					  
					  #include <QMainWindow>
					  #include "viewwidget.h"
					  #include <string>
					  #include <map>
					  
					  QT_BEGIN_NAMESPACE
					  namespace Ui { class MiniDraw; }
					  QT_END_NAMESPACE
					  
					  class MiniDraw : public QMainWindow
					  {
					      Q_OBJECT
					  
					  public:
					      MiniDraw(QWidget *parent = nullptr);
					      ~MiniDraw();
					  
					  private:
					      Ui::MiniDraw *ui;
					  
					      QMenu *mp_menu;
					      QToolBar *mp_toolbar;
					  
					      ViewWidget *mp_viewwidget;  //👈set the view widget as a data member of main view
					  
					  	/* Functions init the actions, button and tool bar*/
					      void createMenu();
					      void createToolBar();
					      void createActions();
					      void createAboutBox();
					  
					      std::map<const char *, QAction*> actions;  //👈here I made a map for recording the action
					      const char *ABOUT = "&About";
					      const char *RECTANGLE = "&Rectangle";
					      const char *LINE = "&Line";
					  };
					  #endif // MINIDRAW_H
					  
					  ```
				- `minidraw.cpp`
					- ``` c++
					  #include "minidraw.h"
					  #include "./ui_minidraw.h"
					  #include <QToolBar>
					  
					  MiniDraw::MiniDraw(QWidget *parent)
					      : QMainWindow(parent)
					      , ui(new Ui::MiniDraw)
					  {
					      ui->setupUi(this);
					      createActions();
					      createToolBar();
					      createMenu();
					  
					      mp_viewwidget = new ViewWidget();
					      setCentralWidget(mp_viewwidget);
					  }
					  
					  void MiniDraw::createActions()
					  {
					      actions[ABOUT] = new QAction(tr(ABOUT), this);
					      actions[LINE] = new QAction(tr(LINE), this);
					      actions[RECTANGLE] = new QAction(tr(RECTANGLE), this);
					  }
					  
					  void MiniDraw::createToolBar()
					  {
					      mp_toolbar = addToolBar(tr("&Tool Bar"));
					      for(auto action : actions)
					      {
					          mp_toolbar->addAction(action.second);
					      }
					  }
					  
					  void MiniDraw::createMenu()
					  {
					      mp_menu = menuBar()->addMenu(tr("&Menu"));
					      for(auto action : actions)
					      {
					          mp_menu->addAction(action.second);
					      }
					  }
					  
					  MiniDraw::~MiniDraw()
					  {
					      delete ui;
					  }
					  ```
				- `main.cpp`
					- ``` c++
					  #include "minidraw.h"
					  
					  #include <QApplication>
					  
					  int main(int argc, char *argv[])
					  {
					    	//👇 a MACRO helps detecting memory leak
					      _CrtSetDbgFlag(_CrtSetDbgFlag(_CRTDBG_REPORT_FLAG) | _CRTDBG_LEAK_CHECK_DF);
					  
					      QApplication a(argc, argv);
					      MiniDraw w;
					      w.show();
					      return a.exec();
					  }
					  
					  ```
	- ## 🌓Complement
	  What is the complement of this subject? e.g. vector-covector, constructor-destructor
	- ## 🤳Applicability
	   What are the situations in which this subject can be applied?
	- ## 🔎Implementation
	   The code or technical stuffs implement this.
	- ## 🕳Pitfalls
	  Be aware of the pitfalls when using this stuffs... (especially considering edge cases)
	- ## 🙋‍♂️Related Elements
	   The closest element to current one, what are their differences?
	- ## 📋Prerequisite
	  Some techniques and objects only work under certain condition.
	- ## 🐍Algorithm
	  Algorithm relates to this stuff..
	- ## 🥼Expert's Advice
	  See what experts addressed.
	- ## 🧱Structure
	  Any other hierarchical issues?