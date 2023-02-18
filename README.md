# Timer Sample GTK3

![images](https://user-images.githubusercontent.com/98597119/219901835-cc6a9f58-4935-483a-9c9c-059783ab1eb8.png)

## Install Eclipse on CentOS

* Enable snaps on CentOS and install Eclipse

* https://snapcraft.io/install/eclipse/centos

## The GTK Project 

* https://www.gtk.org/docs/installations/linux/

* Compiler Command GTK3

~]$ su -

~]# rpm -q centos-release

~]# yum makecache

~]# yum -y clean all

~]# yum -y install epel-release

~]# yum -y update

~]# yum -y upgrade

~]# yum -y install kernel-devel-$(uname -r)

~]# yum -y install make gcc kernel-headers kernel-devel perl dkms bzip2 binutils patch libgomp glibc-headers glibc-devel elfutils-libelf-devel

~]# yum -y install gcc-c++.x86_64 gtk3.x86_64 gtk-devel.x86_64 glib.x86_64 libsigc++20.x86_64 gtkmm30.x86_64 meson.noarch glade3.x86_64

~]# yum -y install vim wget unzip net-tools yum-utils htop NetworkManager-tui

~]# vim timer-sample.c

#include <gtk/gtk.h>

#include <unistd.h>

#include <glib.h>

static GtkWidget *s_label = NULL;

static guint timer_id;

static volatile gboolean s_timer_request_quit = FALSE;

static gboolean label_countup (gpointer user_data)
{
    static gint s_label_count = 0;

    if (s_label != NULL && !s_timer_request_quit) {
        gchar label[256];
        memset (label, 0x0, 256);
        sprintf (label, "count = %d", s_label_count);
        gtk_label_set_text ( GTK_LABEL (s_label), label);
        s_label_count++;
    }
    
    /* TRUE - Returns this function again！ */
    
    return !s_timer_request_quit;
}

static gboolean cb_window_delete_event (GtkWidget *widget, GdkEventAny *event, gpointer user_data)
{
    s_timer_request_quit = TRUE;
    g_source_remove (timer_id);

    return FALSE;
}

static void cb_application_activate (GtkApplication* app, gpointer user_data)
{
    GtkWidget *window;

    window = gtk_application_window_new (app);
    gtk_window_set_title (GTK_WINDOW (window), "Timer Sample");
    gtk_widget_set_size_request (window, 320, 240);
    gtk_window_set_position (GTK_WINDOW (window), GTK_WIN_POS_CENTER_ALWAYS);
    g_signal_connect (window, "delete_event", G_CALLBACK (cb_window_delete_event), NULL);

    s_label = gtk_label_new ("count = 0");
    gtk_container_add (GTK_CONTAINER (window), s_label);

    gtk_widget_show_all (window);

    /* Timer set */
    timer_id = g_timeout_add (1000, (GSourceFunc)label_countup, NULL);
}

int main (int argc, char **argv)
{
    GtkApplication *app;
    int status;

    app = gtk_application_new ("org.gtk3.timer", G_APPLICATION_FLAGS_NONE);
    g_signal_connect (app, "activate", G_CALLBACK (cb_application_activate), NULL);
    status = g_application_run (G_APPLICATION (app), argc, argv);
    g_object_unref (app);

    return status;
}

:x

~]$ gcc `pkg-config --cflags --libs gtk+-3.0` timer-sample.c -o timer-sample

~]$ ./timer-sample
