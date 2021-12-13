<template>
  <div class="text-h3 text-center bgc">Services</div>
  <div class="row bgc q-gutter-md flex-center">
    <div class="col-xs-12 col-sm-6 col-md-2 q-pa-lg">
      <q-card class="my-card bg-transparent no-shadow">
        <img
          class="radius-16"
          src="https://cdn.discordapp.com/attachments/912888928749645896/919898173290450944/cleaning.png"
        />

        <q-card-section class="q-pa-md text-center">
          Thermal Paste Application Services
        </q-card-section>

        <q-card-actions vertical align="center">
          <q-btn
            class="btn"
            label="Learn more"
            icon-right="arrow_forward"
            @click="thermal = true"
          />
        </q-card-actions>
      </q-card>
    </div>

    <div class="col-xs-12 col-sm-6 col-md-2 q-pa-lg">
      <q-card class="my-card bg-transparent no-shadow">
        <img
          class="radius-16"
          src="https://cdn.discordapp.com/attachments/912888928749645896/919898173533728788/sastavljanje-konfiguracije-1.png"
        />

        <q-card-section class="q-pa-md text-center">
          Pc Building & repair services
        </q-card-section>

        <q-card-actions vertical align="center">
          <q-btn
            class="btn"
            label="Learn more"
            icon-right="arrow_forward"
            @click="repair = true"
          />
        </q-card-actions>
      </q-card>
    </div>

    <div class="col-xs-12 col-sm-6 col-md-2 q-pa-lg">
      <q-card class="my-card bg-transparent no-shadow">
        <img
          class="radius-16"
          src="https://cdn.discordapp.com/attachments/912888928749645896/919898173818949663/bekap.png"
        />

        <q-card-section class="q-pa-md text-center">
          Data Backup & Restore Services
        </q-card-section>

        <q-card-actions vertical align="center">
          <q-btn
            class="btn"
            label="Learn more"
            icon-right="arrow_forward"
            @click="data = true"
          />
        </q-card-actions>
      </q-card>
    </div>

    <div class="col-xs-12 col-sm-6 col-md-2 q-pa-lg">
      <q-card class="my-card bg-transparent no-shadow">
        <img class="radius-16" src="https://imgur.com/agsax0M.jpg" />

        <q-card-section class="q-pa-md text-center">
          Security Camera Installation Service
        </q-card-section>

        <q-card-actions vertical align="center">
          <q-btn
            class="btn"
            label="Learn more"
            icon-right="arrow_forward"
            @click="cams = true"
          />
        </q-card-actions>
      </q-card>
    </div>
  </div>

  <q-dialog v-model="thermal">
    <q-card>
      <q-card-section>
        Without thermal paste, there isn't optimal heat transfer between the CPU
        and the heat sink. As such, the CPU gets a lot hotter than it would be
        if you had used paste. If the CPU gets too hot, it will overheat; this
        results in stuttering from throttling, blue screens, and random
        shutdowns.
      </q-card-section>
      <q-card-section class="row flex-center">
        <q-img
          class="radius-16"
          style="width: 500px"
          src="https://i.imgur.com/qkq3mbe.jpg"
        />
      </q-card-section>
      <q-card-section>
        When you're building a PC, you're more excited about the new processor,
        graphics card, and RAM instead of the tube of thermal paste you bought.
        However, thermal paste is vital for your computer's health; without it,
        your PC won't stay on for very long!
      </q-card-section>
      <q-card-section>
        We provide this service just in case you don't feel comfortable doing
        yourself. We have the expertise and the know-how to make it last without
        you having to worry about it.
      </q-card-section>
    </q-card>
  </q-dialog>

  <q-dialog v-model="repair">
    <q-card>
      <q-card-section>
        Computers and laptop repairs are done by experience technician. First, a
        computer diagnosis is performed to detect potential problems. In many
        cases, the cause of the error is determined after only a few minutes and
        can be successfully resolved at your home. Below are examples of some of
        the issues (symptoms).
      </q-card-section>
      <q-card-section class="row flex-center">
        <q-img
          class="radius-16"
          style="width: 500px"
          src="https://i.imgur.com/KmxTJH6.jpeg"
        />
      </q-card-section>
      <q-card-section>
        <strong class="text-h6"
          >The computer crashes frequently or does not start at all</strong
        >

        <br />

        This can be caused by a faulty operating system, an accidentally changed
        BIOS, missing drivers, defective components or other sources of error.
        The technician’s computer diagnosis will provide information about this
        and usually these problems can be corrected on the spot, immediately.
      </q-card-section>

      <q-card-section>
        <strong class="text-h6"
          >Infestation of viruses and malicious programs</strong
        >

        <br />

        Many users have ineffective antivirus programs or an incorrectly set
        firewall to protect the computer. However, these are essential in this
        day and age, as attacks on home computers continue to increase. These
        are usually so-called Trojans, which are hidden in documents, music
        files or pictures. Also, while visiting an unknown website, it is
        possible for a Trojan to be installed unnoticed on the system.

        <br />

        When downloading mostly free programs, unwanted advertising programs are
        often installed. Although they do not attack the computer, they cause a
        lot of trouble with constantly popping up advertising windows.

        <br />
        We can check your computer with an antivirus program and remove all
        types of viruses and malicious programs.
      </q-card-section>

      <q-card-section>
        <strong class="text-h6">Very slow or no internet</strong>

        <br />

        Errors in the router settings, router placement within the house, or
        broken fiber optic cables often cause problems with Internet
        connections. Our technicians check the router settings and cable
        connections so you can surf the Internet at normal speeds.

        <br />
        If no computer part is defective and needs to be replaced, and your
        device does not need to go to a shop, most problems can be solved on the
        spot, immediately. If a part is defective, it may be necessary for a
        replacement part to be ordered. Only in very rare cases must the
        technician take your device with him to carry out the repair in the
        shop.

        <br />
        However, most problems are not caused by defective components, but by a
        faulty operating system, incompatibility, or other errors in the
        installed software.
      </q-card-section>
    </q-card>
  </q-dialog>

  <q-dialog v-model="data">
    <q-card>
      <q-card-section>
        Data is sensitive and invaluable to many people. It can be in the form
        of digital family photos that have been stored on a device for years. It
        can be correspondence that you depend on or digital music that exists
        only as MP3 files on the computer. Nobody wants to give up this data and
        lose it. Disks are, unfortunately, very susceptible to faults, and
        errors sneak into the files over time, so that sometimes data cannot be
        read correctly. In this case, the hard disk must be checked with the
        help of a diagnostic program and, if necessary, defragmented or
        repaired.
      </q-card-section>
      <q-card-section class="row flex-center">
        <q-img
          class="radius-16"
          style="width: 500px"
          src="https://i.imgur.com/hRwLybi.jpeg"
        />
      </q-card-section>
      <q-card-section>
        However, there are situations where the technician discovers that the
        computer’s existing hard drive has a physical defect. This can happen,
        for example, if the hard drive has been hit, has been subject to
        magnetic interference, or simply has age-related wear and tear. In any
        case, however, prompt action is needed to save the existing data. Our
        technicians always have an external hard drive with them, with which a
        fast data backup can be carried out on request. Of course, the
        replacement of the existing hard drive is required here, but, of course,
        the new hard drive arrives without any data. In this case, a complete
        reinstallation of the operating system is required. With the help of the
        technician’s external hard disk and a previous backup of the old hard
        disk, the data can then be copied back to the new hard disk.
      </q-card-section>
      <q-card-section>
        It is always advisable to regularly save valuable data that you cannot
        do without. There are automatic backup programs that can save selected
        directories and files on certain days at a specific time. Our technician
        can install an automatic backup if you wish.
      </q-card-section>
      <q-card-section>
        In some cases, a hard drive failure is so severe that the data cannot be
        restored on-site and the hard drive must be taken back to save the
        valuable data. There are companies that specialize in restoring data and
        they can usually save a large part of it.
      </q-card-section>
    </q-card>
  </q-dialog>

  <q-dialog v-model="cams">
    <q-card>
      <q-card-section>
        We have the ability to install IP or analog commercial surveillance
        camera systems consisting of as little as 4 cameras right up to
        large-scale systems consisting of 300 cameras or more..
      </q-card-section>
      <q-card-section class="row flex-center">
        <q-img
          class="radius-16"
          style="width: 500px"
          src="https://i.imgur.com/dw1rDni.jpeg"
        />
      </q-card-section>
      <q-card-section>
        Camera systems help deter crime and reduce liability by providing an
        unbiased record of events. They can be installed on the exterior or
        interior of a building to monitor sensitive areas such as entrances,
        parking lots, cash rooms, or secure areas of a building. They can also
        be connected to access control systems to provide a record of who is
        entering and exiting a building.
      </q-card-section>
      <q-card-section>
        Any type of business can benefit from a camera system, but the most
        common clients include hotels, hospitals, office buildings, schools,
        retail stores, and government offices.
      </q-card-section>
    </q-card>
  </q-dialog>
</template>

<script>
import { ref, defineComponent } from "vue";

export default defineComponent({
  setup() {
    const thermal = ref(false);
    const repair = ref(false);
    const data = ref(false);
    const cams = ref(false);

    return {
      thermal,
      repair,
      data,
      cams,
    };
  },
});
</script>

<style lang="scss" scoped>
.bgc {
  background-color: #81a1c1;
}
</style>
